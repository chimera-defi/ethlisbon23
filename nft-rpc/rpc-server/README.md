# About 

A public good RPC. Funded by NFT communities. 
This RPC:
- does not censor
- can be used permissionlessly by anyone
- reduces a large centralization vector in Ethereum where 2-3 players control all RPC requests
- Can be faster at getting TXs included in case other RPCs are throttled or slow. 

This repo contains scripts used to setup the server, based on eth2-quickstart. 

# Reproduction steps

Setup a cloud or home server first. With sufficient specs to run a EL and CL client. 

```
git clone https://github.com/chimera-defi/eth2-quickstart.git
// Run through the setup to configure and pre-harden the server. 
// Will install eth1, prysm CL, utils

// We use erigon for this use-case as it supports standalone RPC processes
./erigon.sh

./install_nginx_ssl.sh
// Setup SSL certs and route53 domains for the rpc
```

# Check the RPCs work
```
curl -X POST https://mainnet.sharedtools.org/nounsdaorpc --data '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":32}' -H 'Content-Type: application/json'

curl -X POST https://mainnet.sharedtools.org/apecoinrpc --data '{"jsonrpc":"2.0","method":"eth_chainId","params":[],"id":32}' -H 'Content-Type: application/json'
```

# Frontend interactive story

https://68i5i2rxwzw.typeform.com/to/F8pyb0Gr?typeform-source=68i5i2rxwzw.typeform.com