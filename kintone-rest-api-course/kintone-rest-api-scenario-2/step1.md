First, let's install the Alpaca API from npm.

Run `npm install @kintone/rest-api-client`{{execute}} to install the API.

Now, we can import and initialize our Alpaca module.

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

To start, let's just get your account info.


We can run this code with `node ./main.js`{{execute}}