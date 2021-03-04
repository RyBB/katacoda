kintoneには[rest-api-client](https://github.com/kintone/js-sdk/tree/master/packages/rest-api-client)というSDKがあります。<br/>
今回はこのSDKを使ってNode.js上でkintone REST APIを実行します。

**Copy to Editor**をクリックして以下のコードを右側のエディタにコピーしてください。

<pre class="file" data-filename="main.js" data-target="append">
const API_TOKEN = "YOUR_TOKEN";
const APP_ID = "YOUR_APP_ID";

const { KintoneRestAPIClient } = require('@kintone/rest-api-client');
// クライアントの作成
const client = new KintoneRestAPIClient({
  baseUrl: 'https://cy-sc.cybozu.com',
  auth: {
    apiToken: API_TOKEN
  }
});

// リクエストパラメータの設定
const params = {
  app: APP_ID
};

// レコードの取得
client.record.getRecords(params)
.then((resp) => {
  console.dir(resp.records);
}).catch((err) => {
  console.error(err);
});
</pre>

1行目、2行目の部分を修正してください。<br/>
<br/>
<br/>
次のコマンドをクリックすることでNode.jsが実行できます<br/>
 `node ./main.js`{{execute}}

---
