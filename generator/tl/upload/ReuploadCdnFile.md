# upload.ReuploadCdnFile

Request a reupload of a certain file to a [CDN DC](https://core.telegram.org/cdn).

## Example

::::tabs
:::tab{title="JavaScript"}

```js
const { Api, TelegramClient } = require("telegram");
const { StringSession } = require("telegram/sessions");

const session = new StringSession(""); // You should put your string session here
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
  await client.connect(); // This assumes you have already authenticated with .start()

  const result = await client.invoke(
    new Api.upload.ReuploadCdnFile({
      fileToken: Buffer.from("arbitrary data here"),
      requestToken: Buffer.from("arbitrary data here"),
    })
  );
  console.log(result); // prints the result
})();
```

:::

:::tab{title="TypeScript"}

```ts
import { Api, TelegramClient } from "telegram";
import { StringSession } from "telegram/sessions";

const session = new StringSession(""); // You should put your string session here
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
  await client.connect(); // This assumes you have already authenticated with .start()

  const result: Api.Vector<FileHash> = await client.invoke(
    new Api.upload.ReuploadCdnFile({
      fileToken: Buffer.from("arbitrary data here"),
      requestToken: Buffer.from("arbitrary data here"),
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|       Name       | Type                                          | Description   |
| :--------------: | --------------------------------------------- | ------------- |
|  **fileToken**   | [bytes](https://core.telegram.org/type/bytes) | File token    |
| **requestToken** | [bytes](https://core.telegram.org/type/bytes) | Request token |

## Result

[Vector](https://core.telegram.org/type/Vector%20t)<[FileHash](https://core.telegram.org/type/FileHash)>

## Possible errors

| Code | Type               | Description                     |
| :--: | ------------------ | ------------------------------- |
| 400  | RSA_DECRYPT_FAILED | Internal RSA decryption failed. |

## Can bots use this method?

Yes

## Related pages

#### [Encrypted CDNs for Speed and Security](https://core.telegram.org/cdn)
