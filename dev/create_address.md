# Generate the KTO address
The 'Kto' address is generated in the way of 'ed2515' which is different from that of Ethereum

## Js SDK
You can use the js' kto-utils' library for address generation


Here is an example:
```
$ npm install kto-utils
```
```JavaScript
var KtoUtils=require("kto-utils");
let res=KtoUtils.keyPair();
console.log('To generate address',res)
//--------
To generate address {
  ktoAddress: 'Kto55XQpzF5fXQMtW8HNS6ufMDfYTM1qSeHG8bVywAjgqU3',
  privateKry: '2o3rn2XGWutEZqLpgjWUFGjN2n1z4nKrPwt6iiUCcNtfxs87mztxYAe186j2R5RvEG9M8F9mFRdgkaLMANfb3wUK'
} 
```

The private key restores the public key:
```JavaScript
var KtoUtils=require("kto-utils");
let secretKey = "2XRyFnfbXp4pQMUS2pbxmLprdo7sym4C8cWWGewnsvmPvGF5RkXMFi5rLeRaDD2eG43PB5zX2w3Xi8hft54PXmbN";
secretKey = KtoUtils.decode58(secretKey)
console.log('hex', secretKey)
let ret = KtoUtils.fromSecretKey(Buffer.from(secretKey));
console.log(ret)

```