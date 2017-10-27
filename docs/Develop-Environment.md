# Develop Environment #

## Geth ##
https://github.com/ethereum/go-ethereum/wiki/Private-network

### Build ###
```shell
git clone https://github.com/ethereum/go-ethereum
cd go-ethereum
make geth
sudo ln -s /.../build/bin/geth /usr/local/bin/
```

### Start ###
genesis block
```shell
vi ~/Decentralize-Exchange/genesis.json
```
```json
{
  "alloc"      : {},
  "coinbase"   : "0x0000000000000000000000000000000000000000",
  "difficulty" : "0x20000",
  "extraData"  : "",
  "gasLimit"   : "0x2fefd8",
  "nonce"      : "0x0000000000000000",
  "mixhash"    : "0x0000000000000000000000000000000000000000000000000000000000000000",
  "parentHash" : "0x0000000000000000000000000000000000000000000000000000000000000000",
  "timestamp"  : "0x00",
  "config": {
    "chainId": 1984,
    "homesteadBlock": 0,
    "eip155Block": 0,
    "eip158Block": 0
  }
}
```

create account
```shell
geth --datadir ~/Decentralize-Exchange/ account new
```

initial chain
```shell
geth --datadir ~/Decentralize-Exchange/data init ~/Decentralize-Exchange/genesis.json
```

```shell
geth --identity "DE" --datadir ~/Decentralize-Exchange/data --rpc --rpcapi "db,eth,net,web3,personal" --mine --minerthreads=4 console --rpccorsdomain "http://localhost:8000" --networkid="1984" --unlock f9d41b409352bcaef5939e1db2bd66897fa7937f
```

## Install Explorer ##
```shell
git clone https://github.com/carsenk/explorer

cd explorer
sudo npm install -g bower
npm install
bower install
npm start
```

## Another Explorer ##
https://github.com/etherparty/explorer
