# auth.ImportBotAuthorization

No description found

### [](#example)Example

::::tabs
:::tab{title="JavaScript"}

```js
const { Api, TelegramClient } = require("telegram");
const { StringSession } = require("telegram/sessions");

const session = new StringSession("");
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
  const result = await client.invoke(
    new Api.auth.ImportBotAuthorization({
      flags: 43,
      apiId: 43,
      apiHash: "some string here",
      botAuthToken: "some string here",
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

const session = new StringSession("");
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
  const result: Api.auth.Authorization = await client.invoke(
    new Api.auth.ImportBotAuthorization({
      flags: 43,
      apiId: 43,
      apiHash: "some string here",
      botAuthToken: "some string here",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

### [](#parameters)Parameters

|     Name     | Type   | Description          |
| :----------: | ------ | -------------------- |
|    flags     | int    | No description found |
|    apiId     | int    | No description found |
|   apiHash    | string | No description found |
| botAuthToken | string | No description found |

### [](#result)Result

auth.Authorization

### [](#possible-errors)Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

### [](#can-bots-use-this-method)Can bots use this methd ?

####No

### [](#related-pages)Related pages