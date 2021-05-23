# account.GetTheme

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
    new Api.account.GetTheme({
      format: "some string here",
      theme: new Api.InputTheme({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      documentId: BigInt("-4156887774564"),
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
  const result: Api.Theme = await client.invoke(
    new Api.account.GetTheme({
      format: "some string here",
      theme: new Api.InputTheme({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      documentId: BigInt("-4156887774564"),
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

### [](#parameters)Parameters

|    Name    | Type       | Description          |
| :--------: | ---------- | -------------------- |
|   format   | string     | No description found |
|   theme    | InputTheme | No description found |
| documentId | long       | No description found |

### [](#result)Result

Theme

### [](#possible-errors)Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

### [](#can-bots-use-this-method)Can bots use this methd ?

####No

### [](#related-pages)Related pages