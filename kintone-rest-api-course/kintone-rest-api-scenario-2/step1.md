First, let's install the Alpaca API from npm.

Run `npm install @kintone/rest-api-client`{{execute}} to install the API.

Now, we can import and initialize our Alpaca module.

<pre class="file" data-filename="main.js" data-target="append">

const { KintoneRestAPIClient } = require('@kintone/rest-api-client');
// クライアントの作成
const client = new KintoneRestAPIClient({
  baseUrl: 'https://cy-sc.cybozu.com',
  auth: {
    apiToken: YOUR_TOKEN
  }
});

// リクエストパラメータの設定
const APP_ID = 1;
const RECORD_ID = 1;
const params = {
  app: APP_ID,
  id: RECORD_ID
};

// レコードの取得
client.record.getRecord(params).then((resp) => {
  console.log(resp.record);
}).catch((err) => {
  console.log(err);
});
</pre>

To start, let's just get your account info.


We can run this code with `node ./main.js`{{execute}}