# Ledger wallet provider

Use ledger harware wallet with web3.js

## setup
```bash
$ npm install bloq/ledger-provider --save    # Install local dependencies
```
### Setup of ledger wallet
- Connect ledger wallet with computer
- Unlock wallet
- Turn off browser support in eth app of wallet
- Turn on contract data in eth app of wallet
## usage

```bash
const LedgerWalletProvider = require('ledger-provider')
const Web3 = require("Web3");

async function test() {
    const ledgerWalletProvider = new LedgerWalletProvider(<rpcURL>)

    web3 = new Web3(ledgerWalletProvider)
    let accounts = await web3.eth.getAccounts()
    console.log('accounts', accounts)
    return web3.eth.sendTransaction({
        from: accounts[0],
        to: <to address>,
        value: <amount>
    })
}

test()
    .then(console.log)
    .catch(console.log)


```