# phone.LeaveGroupCall

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
    new Api.phone.LeaveGroupCall({
      call: new Api.InputGroupCall({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      source: 43,
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
  const result: Api.Updates = await client.invoke(
    new Api.phone.LeaveGroupCall({
      call: new Api.InputGroupCall({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      source: 43,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

### [](#parameters)Parameters

|  Name  | Type           | Description          |
| :----: | -------------- | -------------------- |
|  call  | InputGroupCall | No description found |
| source | int            | No description found |

### [](#result)Result

Updates

### [](#possible-errors)Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

### [](#can-bots-use-this-method)Can bots use this methd ?

####No

### [](#related-pages)Related pages