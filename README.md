# Get gas price
```
curl https://public-node.testnet.rsk.co/2.2.0/ -X POST -H "Content-Type: application/json" --data '{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":1}' > .gas-price-testnet.json
```
# Truffle console
Truffle Console connected to RSK network
Connect to RSK regtest (local node)
```
# for local node
truffle console
# for testnet
truffle console --network testnet
```
```
# get last block number
(await web3.eth.getBlockNumber()).toString()
# get network id(for local node network id is 33, for testnet network id is 31)
(await web3.eth.net.getId()).toString()
# get addresses
const accounts = Object.keys(web3.currentProvider.wallets)
accounts
# save account addresses to the file .accounts
await require('fs').promises.writeFile('.accounts', accounts.join('\n'))
# check balance for the first account
(await web3.eth.getBalance(accounts[0])).toString()
# exit truffle console
.exit
```
# Compile a smart contract
```
truffle compile
```
# Deploy a smart contract at testnet
```
truffle migrate --network testnet
```
# References
https://developers.rsk.co/tutorials/ethereum-devs/setup-truffle-oz/
https://developers.rsk.co/tutorials/tokens/create-a-collectable-token/
https://developers.rsk.co/tutorials/ethereum-devs/remix-and-metamask-with-rsk-testnet/
