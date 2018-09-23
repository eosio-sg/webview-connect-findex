[English](https://github.com/eosio-sg/webview-connect-findex/blob/master/README.md)    [简体中文](https://github.com/eosio-sg/webview-connect-findex/blob/master/README.zh-CN.md)

## **Webview-connect-findex**

这里讲述React Native App如何使用webview与Findex交易网站进行通信。实现此功能，只需要在钱包中进行以下几步操作：

1.将example/demo-webview.js 中的组件引入于钱包文件中：<br>
    `const eos = Eos(exampleConfig);` <br>
  例中的eos常量可以根据自己情况从外部（上层组件或者store里面的数据）传入
  
2.在代码中将自己钱包的名字，当前账户，以及用户所用语言版本作为参数放到 WebView的source 的url中：<br>
```javascript
return <WebView onMessage={this.onWebViewMessage}
                ref={webview => {
                  this.myWebView = webview;
                }}
                source={{uri: 'https://example.findex.one?inWallet=tokenPocket&eos_account=examplename1&lang=zh-CN'}}/>
```  

* 若用户没有在钱包中登录，则不传入eos_account;
* 如果没有传入lang，打开findex的默认语言为英文;

3.为了让用户再次确认交易数据，建议在调用eosjs的transaction方法之前，将交易数据解析，展示给用户，让用户选择交易或者取消交易。<br>
```javascript
switch (msgData.targetFunc) {          
  case 'transaction':
    //在此加入展示数据的逻辑，让用户决定是否进行交易
    this[msgData.targetFunc].apply(this, [msgData]);
    break;
}
```

_重要：我们正在改进Findex与此文档，以便更好的被钱包接入，如果使用过程中遇到什么问题，请及时与我们取得联系。_

