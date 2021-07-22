# Bind the Ethereum address
To deploy a smart contract on KorthoChain, users first need to bind their KTO address to an Ethereum address. The user needs to send an HTTP request with a bound address.You must ensure that the user address has at least 0.5 KTO balance before sending the request

## Send bind request
    1. Send a POST request to http://118.193.37.36:2926/BindingAddress by Postman：

![](../images/switchrpc/s5.png)
    
    2、Use curl to send request：
    curl -i -X POST -H "'Content-type':'application/json'" -d '{"ethAddress":"0x76cb9973a1C63b77539b9576a884b35aF42e4740","ktoAddress":"KtoFFxtaSbbqEBNSoPLEDdjZjV5CtQY5fRtvAr9bD5vyaM3","privacy":"3p7xacGL3yeo65bguWQ8417cBfGbFozwRU5PdH1tLKQS8LnxSicFWu1mmmh1H6avzW5GrgDGzFuUSr9VF1vTVoU9"}' http://118.193.37.36:2926/BindingAddress

    Comment：
    {
        "ethAddress":"eth address",
        "ktoAddress":"kto address",
        "privacy":"kto privacykey"
    }
    succeed：{"code":0,"message":"ok","retCode":"hash"}

## Check the bind
    1. Send a GET request to http://118.193.37.36:2926/GetEthAddrByKtoAddr by Postman ：

![](../images/switchrpc/s6.png)

    2、Use curl to send request：
    curl http://118.193.37.36:2926/GetEthAddrByKtoAddr?ktoAddress=KtoFFxtaSbbqEBNSoPLEDdjZjV5CtQY5fRtvAr9bD5vyaM3