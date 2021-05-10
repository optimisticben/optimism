# Changelog

## 0.2.7

### Patch Changes

- 9b7dd4b: Update `scripts/start.sh` to parse the websocket port and pass to geth at runtime

## 0.2.6

### Patch Changes

- a0a0052: Add value parsing to the rollup client
- 20df745: Protect a possible `nil` reference in `eth_call` when the blockchain is empty
- 9f1529c: Update the start script to be more configurable
- 925675d: Update `scripts/start.sh` to regenesis v0.2.0

## 0.2.5

### Patch Changes

- 79f66e9: Use constant execution price, which is set by the sequencer
- 5b9be2e: Correctly set the OVM context based on the L1 values during `eth_call`. This will also set it during `eth_estimateGas`. Add tests for this in the integration tests

## 0.2.4

### Patch Changes

- 7e9ca1e: Add batch API to rollup client
- 6e8fe1b: Removes mockOVM_ECDSAContractAccount and OVM_ProxySequencerEntrypoint, two unused contracts.
- 76c4ceb: Calculate data fees based on if a byte was zero or non-zero

## 0.2.3

### Patch Changes

- d6734f6: Change ROLLUP_BASE_TX_SIZE to camelcase for standard style
- 5e0d0fc: Commit go.sum after a `make test`
- 8a2c24a: Set default timestamp refresh threshold to 3 minutes
- ba2e043: Add `VerifiedIndex` to db and api
- ef40ed7: Allow gas estimation for replicas

## 0.2.2

### Patch Changes

- b290cfe: CPU Optimization by caching ABI methods
- c4266fa: Fix logger error

## 0.2.1

### Patch Changes

- 3b00b7c: bump private package versions to try triggering a tag

## v0.1.3

- Integrate data transport layer
- Refactor `SyncService`
- New RPC Endpoint `eth_getBlockRange`

## v0.1.2

Reduce header cache size to allow L2Geth to spin back up.

## v0.1.1

Pre-minnet fixes.

- gaslimit: fix eth_call (#186)
- rollup: safer historical log syncing (#173)
- config: flag for max acceptable calldata size (#181)
- debug rpc: debug_setL1Head and better l1 timestamp management (#184)
- Fix for hasEmptyAccount (#182)
- gasLimit: error on gas limit too high for queue origin sequencer txs (#180)
- Fixes issue with broken gas limit (#183)

## v0.1.0

Initial Release

- Feature complete for minnet
- OVM runtime implemented for deterministic transaction execution on L1
- Runs in either Sequencer mode or Verifier mode
- `rollup` package includes the `SyncService` for syncing the Canonical
  Transaction Chain
- New configuration options for rollup related features
- No P2P networking
- Maintains RPC compatibility with geth
