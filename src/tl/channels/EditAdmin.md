# channels.EditAdmin

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
    new Api.channels.EditAdmin({
      channel: "username",
      userId: "username",
      adminRights: new Api.ChatAdminRights({
        changeInfo: true,
        postMessages: true,
        editMessages: true,
        deleteMessages: true,
        banUsers: true,
        inviteUsers: true,
        pinMessages: true,
        addAdmins: true,
        anonymous: true,
        manageCall: true,
      }),
      rank: "some string here",
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
    new Api.channels.EditAdmin({
      channel: "username",
      userId: "username",
      adminRights: new Api.ChatAdminRights({
        changeInfo: true,
        postMessages: true,
        editMessages: true,
        deleteMessages: true,
        banUsers: true,
        inviteUsers: true,
        pinMessages: true,
        addAdmins: true,
        anonymous: true,
        manageCall: true,
      }),
      rank: "some string here",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

### [](#parameters)Parameters

|    Name     | Type            | Description          |
| :---------: | --------------- | -------------------- |
|   channel   | InputChannel    | No description found |
|   userId    | InputUser       | No description found |
| adminRights | ChatAdminRights | No description found |
|    rank     | string          | No description found |

### [](#result)Result

Updates

### [](#possible-errors)Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

### [](#can-bots-use-this-method)Can bots use this methd ?

####No

### [](#related-pages)Related pages