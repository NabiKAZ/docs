# payments.AssignAppStoreTransaction

No description found

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
    new Api.payments.AssignAppStoreTransaction({
      transactionId: "some string here",
      receipt: Buffer.from("arbitrary data here"),
      restore: true,
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

  const result: Api.Updates = await client.invoke(
    new Api.payments.AssignAppStoreTransaction({
      transactionId: "some string here",
      receipt: Buffer.from("arbitrary data here"),
      restore: true,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|     Name      | Type   | Description          |
| :-----------: | ------ | -------------------- |
|    restore    | true   | No description found |
| transactionId | string | No description found |
|    receipt    | bytes  | No description found |

## Result

Updates

## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

## Can bots use this method?

No

## Related pages