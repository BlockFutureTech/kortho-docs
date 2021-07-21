# 生成kto地址
`Kto`地址采用不同于以太坊的`ed2515`方式生成

## Js SDK
可以使用js`kto-utils`库进行地址生成


示例如下:
```
$ npm install kto-utils
```
```JavaScript
var KtoUtils=require("kto-utils");
let res=ktoUtils.keyPair();
console.log('生成地址',res)
//--------
生成地址 {
  ktoAddress: 'Kto55XQpzF5fXQMtW8HNS6ufMDfYTM1qSeHG8bVywAjgqU3',
  privateKry: '2o3rn2XGWutEZqLpgjWUFGjN2n1z4nKrPwt6iiUCcNtfxs87mztxYAe186j2R5RvEG9M8F9mFRdgkaLMANfb3wUK'
} 
```

私钥还原出公钥：
```JavaScript
var KtoUtils=require("kto-utils");
let secretKey = "2XRyFnfbXp4pQMUS2pbxmLprdo7sym4C8cWWGewnsvmPvGF5RkXMFi5rLeRaDD2eG43PB5zX2w3Xi8hft54PXmbN";
secretKey = KtoUtils.decode58(secretKey)
console.log('hex', secretKey)
let ret = KtoUtils.fromSecretKey(Buffer.from(secretKey));
console.log(ret)

```