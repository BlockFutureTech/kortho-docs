# Krc20 Token Standard

KorTho is fully compatible with [ERC20](https://eips.ethereum.org/EIPS/eip-20) standard，interfaces and events as follows：

```
// ----------------------------------------------------------------------------
// ERC Token Standard #20 Interface
// https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20-token-standard.md
// ----------------------------------------------------------------------------
contract ERC20Interface {
    function totalSupply() public constant returns (uint);
    function balanceOf(address tokenOwner) public constant returns (uint balance);
    function allowance(address tokenOwner, address spender) public constant returns (uint remaining);
    function transfer(address to, uint tokens) public returns (bool success);
    function approve(address spender, uint tokens) public returns (bool success);
    function transferFrom(address from, address to, uint tokens) public returns (bool success);

    event Transfer(address indexed from, address indexed to, uint tokens);
    event Approval(address indexed tokenOwner, address indexed spender, uint tokens);
}
```

EIP reference：

[eip-20](https://eips.ethereum.org/EIPS/eip-20)

Implemetation reference：

[openzeppelin-contracts](https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/contracts/token/ERC20)


# Test KRC20

| symbol | address                                    | decimals |
| ------ | ------------------------------------------ | -------- |
| KTO    | 0x3335AaBb77bCF592B682ffaBf9DD2184B70ea3cB | 18       |
| WKTO   | 0xd18Acf4a3Fec17B660cA74B160dd417Ce2644f22 | 11       |
| USDT   | 0x289d44257A776edF7dAD62D8D8851838DA81c36B | 18       |
| ETH    | 0xBaa0b76CfE469e67395BA7c9C301b9ae8C279537 | 18       |
| USDK   | 0x86B6F743b6D437b52Ebe1b94265132053d255136 | 18       |
| USDC   | 0xa01E9ce9d185Cd22244C1Bb21903eb30ecF65EF4 | 18       |
| BTC    | 0x28E44f86C25f58Bc8D8dD45bF0873CD4AE363e77 | 18       |
| FIL    | 0x665FdB8D6A39912Dce976CaD90D97ae7fa4774db | 18       |
| UNI    | 0x1464BCeb3c4d4Ed8607A0997016AE65EE92F714b | 18       |
| DAI    | 0x1AE948EB906fF65F44991Bdc6D35670246B8f964 | 18       |
