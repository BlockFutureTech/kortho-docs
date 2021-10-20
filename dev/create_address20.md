# Generate the KTO20 address
> At present, THE Kto20 address is limited to the test network. After the completion of the public test of mining machine, the main network will be updated to support the Kto20 address synchronously
> 
`Kto20`Addresses are generated in the same way as Ethereum addresses

## Generate account
```
const Web3Accounts = require('web3-eth-accounts')

let account = new Web3Accounts().create()
//do not do this on prd env
console.log(`account generated. address: ${account.address}, private key: ${account.privateKey}`)
```

## Constructing Transactions
```
const Web3 = require('web3')
async function transfer(fromAccount, to, value){
    const web3 = new Web3('https://www.kortho-chain.com')
    let chainId = await web3.eth.getChainId()
    let nonce = await web3.eth.getTransactionCount(fromAccount.address)
    let gasPrice = await web3.eth.getGasPrice()

    let unsigned = {
        from: fromAccount.address,
        to,
        value: web3.utils.numberToHex(web3.utils.toWei(value, 'ether')),
        gasPrice,
        nonce,
        chainId,
    }

    unsigned.gas = await web3.eth.estimateGas(unsigned)

    let signed = await fromAccount.signTransaction(unsigned)
    return signed
}
```