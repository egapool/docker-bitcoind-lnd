# egapool/docker-bitcoind-lnd

Origin README [uimarinho/docker-bitcoin-core's README](https://github.com/ruimarinho/docker-bitcoin-core/blob/master/README.md)

## Quick Start (with regtest mode)

```
$ git clone git@github.com:egapool/docker-bitcoind-lnd.git
$ cd docker-bitcoind-lnd
$ docker-compose build
$ docker-compose up -d

// Make genesis block
$ docker exec --user bitcoin bitcoin-server bitcoin-cli -regtest generate 1 
```

## Document

### start mining
```
$ docker exec --user bitcoin bitcoin-server bitcoin-cli -regtest generate 1
[
  "764e9777c9b9a2a5023759e64e2d51b98584eb90f501cfd3f336e1247e3863f8"
]
```

### get mininginfo
```
$docker exec --user bitcoin bitcoin-server bitcoin-cli -regtest getmininginfo
{
  "blocks": 102,
  "currentblockweight": 4000,
  "currentblocktx": 0,
  "difficulty": 4.656542373906925e-10,
  "networkhashps": 8.026730334062129e-07,
  "pooledtx": 0,
  "chain": "regtest",
  "warnings": ""
}
```

### create new address
```
$docker exec --user bitcoin bitcoin-server bitcoin-cli -regtest getnewaddress user_name
```
`user_name` is account name.

### mining
```
$docker exec --user bitcoin bitcoin-server bitcoin-cli -regtest generatetoaddress 2 2N8fXXXXXXXXXXXXXXXXXXXXXXXXXXXX 500000
$docker exec --user bitcoin bitcoin-server bitcoin-cli -regtest generate 100
```
マイニング報酬は100ブロック経過後付与される