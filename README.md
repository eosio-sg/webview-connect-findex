[English](https://github.com/eosio-sg/webview-connect-findex/blob/master/README.md)  [简体中文](https://github.com/eosio-sg/webview-connect-findex/blob/master/README.zh-CN.md)

Webview-connect-Findex

Here we will tell you how embed Findex website in your RN wallet.
Findex can post the transaction data to wallet, the account logged in the wallet sign the data, and broadcast the data signed to EOS mainnet, later,
wallet could also feedback the transaction result to Findex.

To realize the features above, just follow the steps:

1.You may use and strengthen the Component in example/demo-webview.js：
  The const eos can also be given from outside(Outer component or store in Redux)

2.You could see source in WebView's params in the code:
  Please give your wallet name, eos_account logged in the wallet and language as parameters in the url.
  Here is the example: https://example.findex.one?inWallet=tokenPocket&eos_account=examplename1&lang=zh-CN;
  If no account has logged in, eos_account should be discarded;
  English would be the default language if no parameter - lang is given.

3.For better user experience, we strongly suggested that showing transaction data to let user double confirm.

Important：We are still working on Findex and these doc, please contact with us with no hesitation when facing any problem.
