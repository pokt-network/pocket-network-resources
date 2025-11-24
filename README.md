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
| Mainnet   | Seed        | PNF           | EU       | Hetzner     | 1     |
| Mainnet   | Seed        | NodeFleet     | EU       | Velia       | 1     |
| Mainnet   | Seed        | NodeFleet     | US       | Velia       | 1     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |
|           |             |               |          |             | 3     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |

#### Validators:

Any under our control under this cluster.

#### Seed:
- 0ef6de745dec386259a1684b3fb766cdf9fc2e1c@seed-one.p2p.infra.pocket.network:26662

#### P2P Gateway Configuration

Each seed node advertises a unique external port through the P2P gateway, mapping to the internal pod port 26656.

| Seed     | External Address                        | Gateway Listener                 | Internal Pod Port | Status      |
|----------|-----------------------------------------|----------------------------------|-------------------|-------------|
| seed-one | seed-one.p2p.infra.pocket.network:26662 | tcp-p2p-mainnet-seed-one (26662) | 26662             | ✅ Connected |

#### Web Gateway (HTTPS) Endpoints

All seed nodes expose web services through the HTTPS gateway with HTTP/2 support.

| Seed     | RPC Endpoint                      | API Endpoint                      | gRPC Endpoint                      |
|----------|-----------------------------------|-----------------------------------|------------------------------------|
| seed-one | rpc-seed-one.infra.pocket.network | api-seed-one.infra.pocket.network | grpc-seed-one.infra.pocket.network |


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
| --------- | ----------- | ------------- | -------- | ----------- | ----- |
|           |             |               |          |             | 6     |
| --------- | ----------- | ------------- | -------- | ----------- | ----- |


#### Validators:

- 390e516a44f2f46b061c6981f1674e5cf5f0187e@validator-one.p2p.beta.infra.pocket.network:26656
- 56e2dcb89d77d2618cb0d6a63e6d1317cac429ee@validator-two.p2p.beta.infra.pocket.network:26657
- fcdfef0edf9804265812793bfc55dc18e50b8e14@validator-three.p2p.beta.infra.pocket.network:26658
- ee311be309ccd63d897355d585a284291792ad22@validator-four.p2p.beta.infra.pocket.network:26659
- 731e0477afac26f550e5b6c2dc991803f65adaed@validator-five.p2p.beta.infra.pocket.network:26660

#### Seed:
- 61a5c01b3ce4ac6d2d2649652a5e89d5153f09e7@seed-one.p2p.beta.infra.pocket.network:26661


#### P2P Gateway Configuration

Each seed node advertises a unique external port through the P2P gateway, mapping to the internal pod port 26656.

| Seed      | External Address                                    | Gateway Listener         | Internal Pod Port | Status      |
|-----------|-----------------------------------------------------|--------------------------|-------------------|-------------|
| val-one   | validator-one.p2p.beta.infra.pocket.network:26656   | tcp-p2p-one-beta (26656) | 26656             | ✅ Connected |
| val-two   | validator-two.p2p.beta.infra.pocket.network:26657   | tcp-p2p-one-beta (26657) | 26656             | ✅ Connected |
| val-three | validator-three.p2p.beta.infra.pocket.network:26658 | tcp-p2p-one-beta (26658) | 26656             | ✅ Connected |
| val-four  | validator-four.p2p.beta.infra.pocket.network:26659  | tcp-p2p-one-beta (26659) | 26656             | ✅ Connected |
| val-five  | validator-five.p2p.beta.infra.pocket.network:26660  | tcp-p2p-one-beta (26660) | 26656             | ✅ Connected |
| seed-one  | seed-one.p2p.beta.infra.pocket.network:26661        | tcp-p2p-one-beta (26661) | 26656             | ✅ Connected |

#### Web Gateway (HTTPS) Endpoints

All seed nodes expose web services through the HTTPS gateway with HTTP/2 support.

| Seed      | RPC Endpoint                            | API Endpoint                            | gRPC Endpoint                            |
|-----------|-----------------------------------------|-----------------------------------------|------------------------------------------|
| seed-one  | rpc-seed-one.beta.infra.pocket.network  | api-seed-one.beta.infra.pocket.network  | grpc-seed-one.beta.infra.pocket.network  |
| val-one   | rpc-val-one.beta.infra.pocket.network   | api-val-one.beta.infra.pocket.network   | grpc-val-one.beta.infra.pocket.network   |
| val-two   | rpc-val-two.beta.infra.pocket.network   | api-val-two.beta.infra.pocket.network   | grpc-val-two.beta.infra.pocket.network   |
| val-three | rpc-val-three.beta.infra.pocket.network | api-val-three.beta.infra.pocket.network | grpc-val-three.beta.infra.pocket.network |
| val-four  | rpc-val-four.beta.infra.pocket.network  | api-val-four.beta.infra.pocket.network  | grpc-val-four.beta.infra.pocket.network  |
| val-five  | rpc-val-five.beta.infra.pocket.network  | api-val-five.beta.infra.pocket.network  | grpc-val-five.beta.infra.pocket.network  |

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
