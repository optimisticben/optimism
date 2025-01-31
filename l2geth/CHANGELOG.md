# Changelog

## 0.3.1

### Patch Changes

- 9231063: Prevent montonicity errors in the miner

## 0.3.0

### Minor Changes

- b799caa: Updates to use RLP encoded transactions in batches for the `v0.3.0` release

### Patch Changes

- b799caa: Add value parsing to the rollup client
- b799caa: Removes the extra setting of the txmeta in the syncservice and instead sets the raw tx in the txmeta at the rpc layer
- b799caa: Fill in the raw transaction into the txmeta in the `eth_sendTransaction` codepath
- b799caa: Add support for parsed revert reasons in DoEstimateGas
- b799caa: Update minimum response from estimate gas
- b799caa: Add value transfer support to ECDSAContractAccount
- b799caa: Ignore the deprecated type field in the API
- b799caa: Return bytes from both ExecutionManager.run and ExecutionManager.simulateMessage and be sure to properly ABI decode the return values and the nested (bool, returndata)
- b799caa: Block access to RPCs related to signing transactions
- b799caa: Add ExecutionManager return data & RLP encoding
- b799caa: Update gas related things in the RPC to allow transactions with high gas limits and prevent gas estimations from being too small
- 9b7dd4b: Update `scripts/start.sh` to parse the websocket port and pass to geth at runtime
- b799caa: Remove the OVMSigner
- b799caa: Prevent 0 value transactions with calldata via RPC

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
