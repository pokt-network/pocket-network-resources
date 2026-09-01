# Service Cards

On-chain metadata cards for the Pocket services owned by PNF, one JSON file per service.
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
- `serving.sync`: `archive` where the gateway runs an archival probe, `full` otherwise.
- `serving.healthcheck` mirrors the gateway checks: `eth_chainId` pinned to the chain id,
  `eth_syncing == false`, the archival `eth_getBalance` probe with its verified balance,
  and a request-over-websocket check. Chain ids and archival balances are copied from
  `pocket-health-checks.yaml`; keep the two files in sync.
- `specs[]` points at the living Ethereum execution-apis OpenRPC document with no `sha256`.
- `updated` is the date of the last card revision.

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
