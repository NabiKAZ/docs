# messages.SetInlineGameScore

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
    new Api.messages.SetInlineGameScore({
      id: new Api.InputBotInlineMessageID({
        dcId: 43,
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      userId: "username",
      score: 43,
      editMessage: true,
      force: true,
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
  const result: Api.Bool = await client.invoke(
    new Api.messages.SetInlineGameScore({
      id: new Api.InputBotInlineMessageID({
        dcId: 43,
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      userId: "username",
      score: 43,
      editMessage: true,
      force: true,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

### [](#parameters)Parameters

|    Name     | Type                    | Description          |
| :---------: | ----------------------- | -------------------- |
| editMessage | true                    | No description found |
|    force    | true                    | No description found |
|     id      | InputBotInlineMessageID | No description found |
|   userId    | InputUser               | No description found |
|    score    | int                     | No description found |

### [](#result)Result

Bool

### [](#possible-errors)Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

### [](#can-bots-use-this-method)Can bots use this methd ?

####No

### [](#related-pages)Related pages