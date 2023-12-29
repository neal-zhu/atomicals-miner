# Atomicals Javascript Library

> atomicals.xyz
> Documentation: https://docs.atomicals.xyz

![Atomicals](banner.png)

### 声明
1. 这是一个有偿使用的软件，每一次使用本软件进行挖矿，会收取 0.000045 BTC (约合不到 $2)，在挖矿时会自动将手续费打到作者的地址. 如果没有挖到，不需要支付这笔手续费
2. 会持续更新这个代码进行优化，甚至已经有很多优化项在构思实施中
3. 程序并不开源，为了安全起见，请务必不要在使用的地址放太多资产
4. 使用时，请务必先进行测试，确保资产安全以及行为符合预期以后，再继续使用.也推荐大家与官方版本的性能进行对比，看看是否值得使用
5. 当前版本比官方版本快大概 30-40x
6. 以后的其他 token 同样可以使用本软件
7. 本人不对此软件使用导致的资产损失承担任何责任。我唯一可以保证的是这个软件没有任何后门
8. 如果有任何问题，请在推特上联系作者 https://twitter.com/0xKISS
9. windows 电脑上可能会引起杀毒软件报警（甚至删掉代码文件），需要选择忽略。如果介意，请不要使用。如果要使用，可以选用一台虚拟机，保证不要有其他核心资产
10. 请主要使用这个软件进行除 mint-dft 以外的操作，因为涉及到大量代码改动，不保证其他命令还是正确的。如果需要使用，请使用官方的代码
11. 再次重申，这是一个旨在于帮助用户提供帮助同时收取很低费用的软件。它是安全的，但是请对自己的资产安全负责

### 使用方法
1. 安装流程同官方
2. 安装好以后编辑 .env 文件，将 GOWORKER_BIN 设置为符合你操作系统的 binary 名字。
    * windows 电脑，设置为 GOWORKER_BIN=./bin/atomicals-miner-windows.exe
    * mac 电脑，设置为 GOWORKER_BIN=./bin/atomicals-miner-darwin
    * linux 电脑，设置为 GOWORKER_BIN=./bin/atomicals-miner-linux
3. yarn cli mint-dft quark --satsbyte xxx

祝大家挖矿愉快, 早日暴富

### Install, Build and Run Tests

## Install

```
Download the github repo:
git clone https://github.com/atomicals/atomicals-js.git

Build:
# If you don't have yarn installed
# npm install -g yarn

yarn install
yarn run build

See all commands at:

yarn run cli --help
```

### Quick Start - Command Line (CLI)

First install packages and build, then follow the steps here to create your first Atomical and query the status. Use `yarn cli`to get a list of all commands available.

#### 0. Environment File (.env)

The environment file comes with defaults (`.env.example`), but it is highly recommend to install and operate your own ElectrumX server. Web browser communication is possible through the `wss` (secure websockets) interface of ElectrumX.

```
ELECTRUMX_WSS=wss://electrumx.atomicals.xyz:50012

// Optional (defaults to wallet.json)
WALLET_PATH=path-to-wallet.json
```

_ELECTRUMX_WSS_: URL of the ElectrumX with Atomicals support. Note that only `wss` endpoints are accessible from web browsers.

#### 1. Wallet Setup

The purpose of the wallet is to create p2tr (pay-to-taproot) spend scripts and to receive change from the transactions made for the various operations. _Do not put more funds than you can afford to lose, as this is still beta!_

To initialize a new `wallet.json` file that will store your address for receiving change use the `wallet-init` command. Alternatively, you may populate the `wallet.json` manually, ensuring that the address at `m/44'/0'/0'/0/0` is equal to the address and the derivePath is set correctly.

Configure the path in the environment `.env` file to point to your wallet file. defaults to `./wallet.json`

Default:

```
WALLET_PATH=.
WALLET_FILE=wallet.json
```

Update to `wallets/` directory:

```
WALLET_PATH=./wallets
WALLET_FILE=wallet.json
```

Create the wallet:

```
yarn cli wallet-init

>>>

Wallet created at wallet.json
phrase: maple maple maple maple maple maple maple maple maple maple maple maple
Legacy address (for change): 1FXL2CJ9nAC...u3e9Evdsa2pKrPhkag
Derive Path: m/44'/0'/0'/0/0
WIF: L5Sa65gNR6QsBjqK.....r6o4YzcqNRnJ1p4a6GPxqQQ
------------------------------------------------------
```

#### 2. Explore the CLI

```
yarn cli --help
```

#### 3. Quick Commands

Get all of the commands available:

```
yarn cli --help
```

Read the documentation at https://docs.atomicals.xyz

## ElectrumX Server RPC Interface

See updated ElectrumX (https://github.com/atomicals/atomicals-electrumx)

## Any questions or ideas?

https://atomicals.xyz

https://x.com/atomicalsxyz (X - Formerly Twitter)

## Donate to Atomicals Development

We greatly appreciate any donation to help support Atomicals Protocol development. We worked out of passion and kindness for the world, we believe this technology must exist and be free for all to use. Bitcoin is our one hope for freedom and digital sovereignty and we intend to do our best to make it a reality.

BTC: bc1pa5hvv3w3wjwfktd63zcng6yeccxg9aa90e34n9jrjw3thgc52reqxw6has

![Donate to Atomicals Development](donate.png)
