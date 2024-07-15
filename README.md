# App template for ZKCross application

This repo is a sample application in RUST which is compiled to WASM and runs in zkc-node.
The trustless part are the transaction handling part whose execution is proved using the ZKWASM proving service and the final proofs are verified onchain with settlement callbacks.

## Project Structure

```
├── example
│   ├── Cargo.toml
│   ├── Makefile
│   ├── publish.sh
│   └── src
│       ├── config.rs
│       ├── events.rs
│       ├── lib.rs
│       ├── settlement.rs
│       └── state.rs
├── README.md
└── ts
    ├── package.json
    ├── src
    │   ├── index.ts
    │   ├── query.ts
    │   ├── rpc.ts
    │   └── sign.ts
    └── tsconfig.json
```

## This project consists of

* example/
A backend program (written in Rust), which specifies a computation that will be executed and proven;

* ts/
Example ts code used to interact with backend program which underlaying is send transaction to zkc-node trigger backend program execution.

## Depoly steps

* Build Wasm binary

```
cd example
make
```

And wasm binary will be at the pkg/ directory

* Pubulish Wasm binary

```
Run build.sh which will publish the Wasm binary to zkc-node
```

* Interact with Wasm backend in ts

```
cd ts
npm install; 
npm index.js
```

You will see the transcation in ZKCross Explorer(tbd) which including the zkc transaction, the zkProof and the Settlement transaction

## More information

[ZKCross Doc](https://docs.zkcross.org/)
