# @computesdk/tensorlake

## 0.1.2

### Patch Changes

- a1405358: Remove hardcoded default values for `image`, `cpu`, `memoryMb`. Use the new `diskMb` option to set the ephemeral disk size.

## 0.1.1

### Patch Changes

- e07d46f: Fix `timeout` unit mismatch in the Tensorlake provider. `config.timeout` (passed to `tensorlake({ timeout: ... })`) was being forwarded to the underlying SDK as seconds while `options.timeout` (passed to `compute.sandbox.create({ timeout: ... })`) was correctly treated as milliseconds, contradicting the `TensorlakeConfig` interface comment. Both inputs are now consistently milliseconds and converted to seconds at the SDK boundary, matching the convention used by every other ComputeSDK provider.

## 0.1.0

### Minor Changes

- b4ad62c: Add `@computesdk/tensorlake` provider for stateful MicroVM sandboxes powered by Tensorlake (https://tensorlake.ai), aimed at agentic applications and LLM-generated code execution. Wraps the `tensorlake` SDK and is auto-detected by the `computesdk` gateway via the `TENSORLAKE_API_KEY` environment variable.

## 0.0.1

### Patch Changes

- Initial release of the Tensorlake provider for ComputeSDK
