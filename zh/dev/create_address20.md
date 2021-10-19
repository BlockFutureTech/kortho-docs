# 生成kto20地址
> 目前Kto20地址仅限于测试网，等待矿机公测完成之后，主网将同步更新支持Kto20地址
> 
`Kto20`地址采用与以太坊地址一样的生成方式

## 生成账户
```
const Web3Accounts = require('web3-eth-accounts')

let account = new Web3Accounts().create()
//do not do this on prd env
console.log(`account generated. address: ${account.address}, private key: ${account.privateKey}`)
```

## 构造交易
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