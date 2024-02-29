# hardhat-manta

Hardhat plugin for manta Developers.

## Features

mantaScan Contract Verification

## Prerequisites

Before the installation steps you need to have your hardhat project initialized using the command

```bash
npx hardhat init
```

Make sure to have dependencies installed!

## Installation

Use the following command to install

```bash
npm i hardhat-manta --save-dev
```

Import the plugin in your `hardhat.config.js`:

```js
require("hardhat-manta");
```

Or if you are using TypeScript, in your `hardhat.config.ts`:

```ts
import "hardhat-manta";
```

Remove / Comment the import for `@nomicfoundation/hardhat-toolbox`

Add the following configuration to the `config` object in `hardhat.config.js`.

```js
networks: {
        mantaGoerli: {
            // can be replaced with the RPC url of your choice.
            url: "https://goerli-rollup.manta.io/rpc",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        },
        mantaOne: {
            url: "https://1rpc.io/manta",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        }
    },
    etherscan: {
        apiKey: {
            mantaGoerli: "<OPTIMISMSCAN_API_KEY>",
            mantaOne: "<OPTIMISMSCAN_API_KEY>"
        },
    },
```

Verify your contracts using the following command (Make sure your contracts are compiled before verification)

manta Goerli Testnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network mantaGoerli
```

manta Mainnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network mantaOne
```
