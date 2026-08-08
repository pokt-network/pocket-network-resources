# Pocket Network Resources
Common Resources in use on the Pocket Network Protocol

## Network Snapshots

- Main snapshots dashboard: https://sync.easy2stake.com/d/ce1jmvhesy1hce/state-sync-server?var-chain_id=pocket
- Stratos downloader for fast decentralized snapshot sync: https://github.com/easy2stake/poktsnap/tree/main/oneshot-downloader
- Backup http resource: https://snaps.easy2stake.com/pocket/

## Sauron Access

#### Mainnet

- RPC: https://sauron-rpc.infra.pocket.network
- REST: https://sauron-api.infra.pocket.network
- gRPC: sauron-grpc.infra.pocket.network:443 (secure)

#### Testnet

- RPC: https://sauron-rpc.beta.infra.pocket.network
- REST: https://sauron-api.beta.infra.pocket.network
- gRPC: sauron-grpc.beta.infra.pocket.network:443 (secure)

## Mainnet Nodes Distribution

This section describes the node distribution for the Pocket Network Mainnet

| Network   | Node Type   | Operator      | Region   | Provider    | Count |
|-----------|-------------|---------------|----------|-------------|-------|
| Mainnet   | Seed        | PNF           | EU       | Hetzner     | 3     |
| Mainnet   | Seed        | NodeFleet     | EU       | Velia       | 1     |
| Mainnet   | Seed        | NodeFleet     | US       | Velia       | 1     |
| Mainnet   | Validator   | NodeFleet     | EU       | Velia       | 3     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |
|           |             |               |          |             | 8     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |

#### Validators:

Any under our control under this cluster.

##### NodeFleet Mainnet Validators (162.19.222.116)

| Validator       | Node ID                                                    | P2P Address                    |
|-----------------|------------------------------------------------------------|--------------------------------|
| nodefleet       | 738da6af6a77f24183cb0e1bd8bc696d47f567e2                  | 162.19.222.116:26661           |
| poktpool        | d96dee22d9854aa5bbb468d9089306921ee9b27a                  | 162.19.222.116:26663           |
| poktpool2       | 239367384ee74911222e1715a7bbfb8c7ba7c31d                  | 162.19.222.116:26662           |

#### Seed:
- 0ef6de745dec386259a1684b3fb766cdf9fc2e1c@seed-one.p2p.infra.pocket.network:26662
- e3f1a09e045433199c94172ef0d6fc9ab7212ad7@seed-two.p2p.infra.pocket.network:26663
- ba32c91950451643b394c487fc15ab4b75364e06@seed-three.p2p.infra.pocket.network:26664
- 3ea9161a71a3a86823002bed5b0caa20431ca377@seed1.shannon-mainnet.eu.nodefleet.net:26671
- 06edc8bbbc7a3c9c7a6a1d9c7492fb5c3b262f1e@seed1.shannon-mainnet.us.nodefleet.net:26680

#### P2P Gateway Configuration

Each seed node advertises a unique external port through the P2P gateway, mapping to the internal pod port 26656.

| Seed                  | External Address                               | Operator   | Region | Internal Port |
|-----------------------|------------------------------------------------|------------|--------|---------------|
| seed-one              | seed-one.p2p.infra.pocket.network:26662        | PNF        | EU     | 26656         |
| seed-two              | seed-two.p2p.infra.pocket.network:26663        | PNF        | EU     | 26656         |
| seed-three            | seed-three.p2p.infra.pocket.network:26664      | PNF        | EU     | 26656         |
| nodefleet-seed1-eu    | seed1.shannon-mainnet.eu.nodefleet.net:26671   | NodeFleet  | EU     | 26670         |
| nodefleet-seed1-us    | seed1.shannon-mainnet.us.nodefleet.net:26680   | NodeFleet  | US     | 26680         |

#### Web Gateway (HTTPS) Endpoints

All seed nodes expose web services through the HTTPS gateway with HTTP/2 support.

| Seed                 | RPC Endpoint                                     | API Endpoint                                     | gRPC Endpoint                                     |
|----------------------|--------------------------------------------------|--------------------------------------------------|---------------------------------------------------|
| seed-one (PNF)       | rpc-seed-one.infra.pocket.network                | api-seed-one.infra.pocket.network                | grpc-seed-one.infra.pocket.network                |
| seed-two (PNF)       | rpc-seed-two.infra.pocket.network                | api-seed-two.infra.pocket.network                | grpc-seed-two.infra.pocket.network                |
| seed-three (PNF)     | rpc-seed-three.infra.pocket.network              | api-seed-three.infra.pocket.network              | grpc-seed-three.infra.pocket.network              |
| seed1-eu (NodeFleet) | rpc.seed1.shannon-mainnet.eu.nodefleet.net       | api.seed1.shannon-mainnet.eu.nodefleet.net       | grpc.seed1.shannon-mainnet.eu.nodefleet.net       |
| seed1-us (NodeFleet) | rpc.seed1.shannon-mainnet.us.nodefleet.net       | api.seed1.shannon-mainnet.us.nodefleet.net       | grpc.seed1.shannon-mainnet.us.nodefleet.net       |
| validator1 (NodeFleet) | rpc.validator1.shannon-mainnet.eu.nodefleet.net | api.validator1.shannon-mainnet.eu.nodefleet.net | —                                                 |
| validator2 (NodeFleet) | rpc.validator2.shannon-mainnet.eu.nodefleet.net | api.validator2.shannon-mainnet.eu.nodefleet.net | —                                                 |
| validator3 (NodeFleet) | rpc.validator3.shannon-mainnet.eu.nodefleet.net | api.validator3.shannon-mainnet.eu.nodefleet.net | —                                                 |


## Testnet Nodes Distribution

This section describes the node distribution for the Pocket Network Testnet (aka as beta)

| Network   | Node Type   | Operator      | Region   | Provider    | Count |
|-----------|-------------|---------------|----------|-------------|-------|
| Beta      | Seed        | PNF           | EU       | Hetzner     | 1     |
| Beta      | Seed        | NodeFleet     | EU       | Velia       | 1     |
| Beta      | Seed        | NodeFleet     | US       | Velia       | 1     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |
|           |             |               |          |             | 3     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |
| Beta      | Validator   | PNF           | EU       | Hetzner     | 5     |
| Beta      | Validator   | NodeFleet     | EU       | Velia       | 1     |
| Beta      | Validator   | NodeFleet     | US       | Velia       | 1     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |
|           |             |               |          |             | 7     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |


#### Validators:

- 390e516a44f2f46b061c6981f1674e5cf5f0187e@validator-one.p2p.beta.infra.pocket.network:26656
- 56e2dcb89d77d2618cb0d6a63e6d1317cac429ee@validator-two.p2p.beta.infra.pocket.network:26657
- fcdfef0edf9804265812793bfc55dc18e50b8e14@validator-three.p2p.beta.infra.pocket.network:26658
- ee311be309ccd63d897355d585a284291792ad22@validator-four.p2p.beta.infra.pocket.network:26659
- 731e0477afac26f550e5b6c2dc991803f65adaed@validator-five.p2p.beta.infra.pocket.network:26660
- 7779df686cf2d9cdf6834ae18481c87512d6bbfe@validator1.shannon-beta.eu.nodefleet.net:26676
- 6d7a4dc2c6ae3f09835c22c17e52928bb4280ee6@validator1.shannon-beta.us.nodefleet.net:26676

#### Seed:
- 61a5c01b3ce4ac6d2d2649652a5e89d5153f09e7@seed-one.p2p.beta.infra.pocket.network:26661
- d641bac695e4d96a1098d84aff96fbceaccbf7da@seed1.shannon-beta.eu.nodefleet.net:26679
- 71c120dd88d75e250841557c8b1eec6198d66a0a@seed1.shannon-beta.us.nodefleet.net:26671


#### P2P Gateway Configuration

Each seed node advertises a unique external port through the P2P gateway, mapping to the internal pod port 26656.

| Node                      | External Address                                    | Operator  | Region | Internal Port | Status      |
|---------------------------|-----------------------------------------------------|-----------|--------|---------------|-------------|
| val-one (PNF)             | validator-one.p2p.beta.infra.pocket.network:26656   | PNF       | EU     | 26656         | ✅ Connected |
| val-two (PNF)             | validator-two.p2p.beta.infra.pocket.network:26657   | PNF       | EU     | 26656         | ✅ Connected |
| val-three (PNF)           | validator-three.p2p.beta.infra.pocket.network:26658 | PNF       | EU     | 26656         | ✅ Connected |
| val-four (PNF)            | validator-four.p2p.beta.infra.pocket.network:26659  | PNF       | EU     | 26656         | ✅ Connected |
| val-five (PNF)            | validator-five.p2p.beta.infra.pocket.network:26660  | PNF       | EU     | 26656         | ✅ Connected |
| seed-one (PNF)            | seed-one.p2p.beta.infra.pocket.network:26661        | PNF       | EU     | 26656         | ✅ Connected |
| seed1-eu (NodeFleet)      | seed1.shannon-beta.eu.nodefleet.net:26679           | NodeFleet | EU     | 26671         | ✅ Connected |
| seed1-us (NodeFleet)      | seed1.shannon-beta.us.nodefleet.net:26671           | NodeFleet | US     | 26671         | ✅ Connected |
| validator1-eu (NodeFleet) | validator1.shannon-beta.eu.nodefleet.net:26676      | NodeFleet | EU     | 26656         | ✅ Connected |
| validator1-us (NodeFleet) | validator1.shannon-beta.us.nodefleet.net:26676      | NodeFleet | US     | 26656         | ✅ Connected |

#### Web Gateway (HTTPS) Endpoints

All seed nodes expose web services through the HTTPS gateway with HTTP/2 support.

| Node                      | RPC Endpoint                                       | API Endpoint                                       | gRPC Endpoint                                       |
|---------------------------|----------------------------------------------------|----------------------------------------------------|-----------------------------------------------------|
| seed-one (PNF)            | rpc-seed-one.beta.infra.pocket.network             | api-seed-one.beta.infra.pocket.network             | grpc-seed-one.beta.infra.pocket.network             |
| val-one (PNF)             | rpc-val-one.beta.infra.pocket.network              | api-val-one.beta.infra.pocket.network              | grpc-val-one.beta.infra.pocket.network              |
| val-two (PNF)             | rpc-val-two.beta.infra.pocket.network              | api-val-two.beta.infra.pocket.network              | grpc-val-two.beta.infra.pocket.network              |
| val-three (PNF)           | rpc-val-three.beta.infra.pocket.network            | api-val-three.beta.infra.pocket.network            | grpc-val-three.beta.infra.pocket.network            |
| val-four (PNF)            | rpc-val-four.beta.infra.pocket.network             | api-val-four.beta.infra.pocket.network             | grpc-val-four.beta.infra.pocket.network             |
| val-five (PNF)            | rpc-val-five.beta.infra.pocket.network             | api-val-five.beta.infra.pocket.network             | grpc-val-five.beta.infra.pocket.network             |
| seed1-eu (NodeFleet)      | rpc.seed1.shannon-beta.eu.nodefleet.net            | api.seed1.shannon-beta.eu.nodefleet.net            | grpc.seed1.shannon-beta.eu.nodefleet.net            |
| seed1-us (NodeFleet)      | rpc.seed1.shannon-beta.us.nodefleet.net            | api.seed1.shannon-beta.us.nodefleet.net            | grpc.seed1.shannon-beta.us.nodefleet.net            |
| validator1-eu (NodeFleet) | rpc.validator1.shannon-beta.eu.nodefleet.net       | api.validator1.shannon-beta.eu.nodefleet.net       | —                                                   |
| validator1-us (NodeFleet) | rpc.validator1.shannon-beta.us.nodefleet.net       | api.validator1.shannon-beta.us.nodefleet.net       | —                                                   |

---

## Connectivity Tests

### P2P TCP Connectivity

Test TCP connectivity to each seed node's P2P port and verify node identity:

```bash
P2P=[P2P_EXTERNAL_ADDRESS] \
RPC=[RPC_GATEWAY_ADDRESS] \
timeout 3 nc -zv $P2P 26661 && \
curl -s https://$RPC/status | \
jq -r '"✅ Moniker: " + .result.node_info.moniker + " | P2P Listen: " + .result.node_info.listen_addr'
```

This verifies both TCP connectives and confirms the correct node is responding via its moniker.

### Web Endpoint Tests

Test HTTPS endpoints for each seed node:

```bash
# Check RPC Endpoint
curl -s https://${RPC_ENDPOINT}/status | jq -r '.result.node_info.moniker'
# Check API Endpoint
curl -s https://${API_ENDPOINT}/cosmos/base/tendermint/v1beta1/node_info | jq -r '.default_node_info.moniker'
# Check gRPC Endpoint
grpcurl -plaintext ${GRPC_HOST}:${GRPC_PORT} list
```

### HTTP/2 Verification

Verify HTTP/2 is enabled:

```bash
# Check ALPN negotiation and HTTP/2
curl -v --http2 https://${RPC_ENDPOINT}/status 2>&1 | grep -E "ALPN.*h2|using HTTP/2"
# Check response headers
curl -sI --http2 https://${API_ENDPOINT}/cosmos/base/tendermint/v1beta1/node_info | grep "HTTP/"
```
