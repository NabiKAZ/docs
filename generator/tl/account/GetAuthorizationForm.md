# account.GetAuthorizationForm

Returns a Telegram Passport authorization form for sharing data with a service

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
    new Api.account.GetAuthorizationForm({
      botId: BigInt("-4156887774564"),
      scope: "some string here",
      publicKey: "some string here",
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

  const result: Api.account.AuthorizationForm = await client.invoke(
    new Api.account.GetAuthorizationForm({
      botId: BigInt("-4156887774564"),
      scope: "some string here",
      publicKey: "some string here",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|     Name      | Type                                            | Description                                              |
| :-----------: | ----------------------------------------------- | -------------------------------------------------------- |
|   **botId**   | [long](https://core.telegram.org/type/long)     | User identifier of the service's bot                     |
|   **scope**   | [string](https://core.telegram.org/type/string) | Telegram Passport element types requested by the service |
| **publicKey** | [string](https://core.telegram.org/type/string) | Service's public key                                     |

## Result

[account.AuthorizationForm](https://core.telegram.org/type/account.AuthorizationForm)

## Possible errors

| Code | Type                | Description               |
| :--: | ------------------- | ------------------------- |
| 400  | PUBLIC_KEY_REQUIRED | A public key is required. |

## Can bots use this method?

No

## Related pages
