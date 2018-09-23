[English](https://github.com/eosio-sg/webview-connect-findex/blob/master/README.md)    [简体中文](https://github.com/eosio-sg/webview-connect-findex/blob/master/README.zh-CN.md)

## **Webview-connect-findex**

Here we will tell you how embed Findex website in your RN wallet. Just follow the steps:

1.You may use directly or strengthen the Component in example/demo-webview.js:<br>

2.Give your wallet name, eos_account logged in the wallet and language as parameters in the url.
```javascript
return <WebView onMessage={this.onWebViewMessage}
                ref={webview => {
                  this.myWebView = webview;
                }}
                source={{uri: 'https://example.findex.one?inWallet=tokenPocket&eos_account=examplename1&lang=zh-CN'}}/>
```  
*  If no account has logged in, eos_account should be discarded;
*  English would be the default language if no parameter - lang is given.

3.For better user experience, we strongly suggested that showing transaction data to let user double confirm.
```javascript
switch (msgData.targetFunc) {          
  case 'transaction':
    //Show transaction detail to users.
    this[msgData.targetFunc].apply(this, [msgData]);
    break;
}
```

_Important：We are still working on Findex and these doc, please contact with us with no hesitation when facing any problem._
