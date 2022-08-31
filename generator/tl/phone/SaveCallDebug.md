# phone.SaveCallDebug

Send phone call debug data to server

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
    new Api.phone.SaveCallDebug({
      peer: new Api.InputPhoneCall({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      debug: new Api.DataJSON({
        data: "some string here",
      }),
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

  const result: Api.Bool = await client.invoke(
    new Api.phone.SaveCallDebug({
      peer: new Api.InputPhoneCall({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      debug: new Api.DataJSON({
        data: "some string here",
      }),
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|   Name    | Type                                                            | Description                              |
| :-------: | --------------------------------------------------------------- | ---------------------------------------- |
| **peer**  | [InputPhoneCall](https://core.telegram.org/type/InputPhoneCall) | Phone call                               |
| **debug** | [DataJSON](https://core.telegram.org/type/DataJSON)             | Debug statistics obtained from libtgvoip |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type              | Description                               |
| :--: | ----------------- | ----------------------------------------- |
| 400  | CALL_PEER_INVALID | The provided call peer object is invalid. |
| 400  | DATA_JSON_INVALID | The provided JSON data is invalid.        |

## Can bots use this method?

No

## Related pages
