# phone.SaveDefaultGroupCallJoinAs

Set the default peer that will be used to join a group call in a specific dialog.

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
    new Api.phone.SaveDefaultGroupCallJoinAs({
      peer: "username",
      joinAs: "username",
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
    new Api.phone.SaveDefaultGroupCallJoinAs({
      peer: "username",
      joinAs: "username",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|    Name    | Type                                                  | Description                                                                                                            |
| :--------: | ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
|  **peer**  | [InputPeer](https://core.telegram.org/type/InputPeer) | The dialog                                                                                                             |
| **joinAs** | [InputPeer](https://core.telegram.org/type/InputPeer) | The default peer that will be used to join group calls in this dialog, presenting yourself as a specific user/channel. |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

## Can bots use this method?

No

## Related pages
