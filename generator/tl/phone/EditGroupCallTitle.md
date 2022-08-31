# phone.EditGroupCallTitle

Edit the title of a group call or livestream

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
    new Api.phone.EditGroupCallTitle({
      call: new Api.InputGroupCall({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      title: "My very normal title",
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
    new Api.phone.EditGroupCallTitle({
      call: new Api.InputGroupCall({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      title: "My very normal title",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|   Name    | Type                                                            | Description |
| :-------: | --------------------------------------------------------------- | ----------- |
| **call**  | [InputGroupCall](https://core.telegram.org/type/InputGroupCall) | Group call  |
| **title** | [string](https://core.telegram.org/type/string)                 | New title   |

## Result

[Updates](https://core.telegram.org/type/Updates)

## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

## Can bots use this method?

No

## Related pages
