# rs-soroban-sdk

> **Temporary fork for [Kanatoko](https://github.com/roman-karpovich/kanatoko).**
> Branch `kanatoko-p29` (tag `v29.0.0-kanatoko.1`) is upstream `v28.0.0` with
> the `soroban-env-*` crates moved to the published 29.0.0 release, so Kanatoko
> can run on Protocol 29 before an official `soroban-sdk` 29 exists. It is not
> published to crates.io and will be dropped once the official `soroban-sdk` 29
> ships. Use the official [stellar/rs-soroban-sdk](https://github.com/stellar/rs-soroban-sdk)
> for anything else.

Rust SDK for building contracts that can be deployed on the [Stellar] network and execute in the [Soroban] runtime.

Rust Docs: https://docs.rs/soroban-sdk

Stellar Developer Docs: https://developers.stellar.org

[Soroban]: https://developers.stellar.org/docs/build/smart-contracts/overview
[Stellar]: https://stellar.org

## Support

The two most recent soroban-sdk major releases are supported with critical security fixes.
Critical security issues may be backported to earlier versions if practical, but not guaranteed.
General bugs are only fixed on, and new features are only added to, the latest major release.

## Build Target

Contracts must be built for the `wasm32v1-none` target, available with Rust 1.84+. It is the only
wasm target supported by the Soroban runtime on Stellar.

Build contracts with `stellar contract build` from [stellar-cli], which targets `wasm32v1-none` and
applies the build settings the Soroban runtime requires. Do not build contracts with `cargo build`.
As of soroban-sdk v28, [stellar-cli] v25.2.0 or newer is required.

The `wasm32-unknown-unknown` target is not supported when building with Rust 1.82 or newer, because
on those versions the target enables wasm features (reference-types, multi-value) that the Soroban
environment does not support and that cannot be easily disabled. Building for
`wasm32-unknown-unknown` on Rust 1.82+ produces a build error.

[stellar-cli]: https://github.com/stellar/stellar-cli

## Contributing

Contributing to the SDK? Read [CONTRIBUTING.md](CONTRIBUTING.md).
