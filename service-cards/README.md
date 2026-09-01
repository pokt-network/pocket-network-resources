# Service Cards

On-chain metadata cards for the Pocket services owned by PNF, one JSON file per service:
every PNF-owned service with at least one staked supplier (77 as of 2026-09-01). Services with
zero suppliers (duplicates, dormant chains, AI model ids) are deliberately left without a card.
Cards are stored in `Service.metadata.card` and follow the `pocket-service-card/v1` schema
(`pkg/cards/service_card.schema.json` in poktroll, prose in `docs/pocket_cards.md`).

The chain enforces size only. Every field in these cards is an owner assertion for two audiences:
consumers deciding how to call the service, and node runners deciding what to run.

## Layout

```
service-cards/
  README.md
  cards/<id>.json    # one card per service id
```

## Conventions

- `rpc_types[].intent`: `expected` where the gateway health-checks the transport
  (`pocket-health-checks.yaml`), `optional` otherwise. Intent is not enforced by anything.
- Cosmos SDK services: `JSON_RPC` means CometBFT's JSON-RPC mode on the RPC port (:26657,
  `POST /` with a jsonrpc envelope), which is what the gateway's `status`/`health` checks send.
  `COMET_BFT` is the same server addressed URI-style (`GET /status`). Websocket subscriptions
  are on that same port at `/websocket`. `REST` is the gRPC-gateway on :1317, `GRPC` is :9090.
  On EVM-enabled Cosmos chains the gateway probes EVM on `JSON_RPC` (kava, sei, xrplevm), so
  there `JSON_RPC` is the :8545 endpoint and the card says so.
- Chain-id assertions: `eth_chainId` for EVM, `node_info.network` for CometBFT, genesis hash for
  Solana, `chain_id` for NEAR, `sui_getChainIdentifier` for Sui, `getblockchaininfo.chain` for
  Bitcoin, `genesis_validators_root` for the Beacon API.
- `serving.sync`: `archive` where the gateway runs an archival probe, `full` otherwise.
- `serving.healthcheck` mirrors the gateway checks: `eth_chainId` pinned to the chain id,
  `eth_syncing == false`, the archival `eth_getBalance` probe with its verified balance,
  and a request-over-websocket check. Chain ids and archival balances are copied from
  `pocket-health-checks.yaml`; keep the two files in sync.
- `serving.docs`: the node-operator run guide for that chain (official docs page where one exists,
  otherwise the node's GitHub repository). `docs` at the top level is the consumer-facing API
  documentation. Both URLs were checked reachable on the card's `updated` date.
- `specs[]` points at the living Ethereum execution-apis OpenRPC document with no `sha256`.
- `updated` is the date of the last card revision.

## Verification status

Every card's `JSON_RPC`, `REST` and `COMET_BFT` probes were executed against public endpoints on
2026-09-01 and the `expect.matches` values confirmed live, with these exceptions, each also noted
in the card itself:

- `bitcoin`: no public RPC; chain string from Bitcoin Core semantics.
- `stargaze`: chain id from the cosmos chain-registry; public RPCs did not answer.
- `taiko-hekla-testnet`: public RPC retired; chain id from chainlist.
- Archival `eth_getBalance` probes on `arb-one`, `blast`, `bsc`, `xrplevm`: public endpoints are
  pruned; balances come from `pocket-health-checks.yaml`, verified by the gateway team against
  archival nodes.
- `WEBSOCKET` probes were not executed (HTTP-only verification run).

Chain ids were cross-checked against chainlist (EVM) and the cosmos chain-registry (CometBFT
chains) independently of the gateway config. Implementations, versions, ports and disk sizes are
owner assertions from project documentation, not measured.

## Validate

```bash
for f in cards/*.json; do pocketd tx service validate-card "$f"; done
```

## Publish

Signer must be the service owner. Publishing uses `pocketd tx service edit-service --config`
with a batch file that lists each service id, its current `compute_units_per_relay`, and the
`card_file` path. That batch file is operator tooling and does not live here: it embeds live
pricing values that must be re-read from chain before every publish, since a stale value
would change pricing.

```bash
pocketd q service show-service eth --network=main            # read the card back after publishing
```

Services whose card already matches on-chain byte-for-byte are skipped by the CLI.
