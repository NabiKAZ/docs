# channels.SetDiscussionGroup

Associate a group to a channel as [discussion group](https://core.telegram.org/api/discussion) for that channel

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
    new Api.channels.SetDiscussionGroup({
      broadcast: "username",
      group: "username",
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
    new Api.channels.SetDiscussionGroup({
      broadcast: "username",
      group: "username",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|     Name      | Type                                                        | Description                                                                              |
| :-----------: | ----------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **broadcast** | [InputChannel](https://core.telegram.org/type/InputChannel) | Channel                                                                                  |
|   **group**   | [InputChannel](https://core.telegram.org/type/InputChannel) | [Discussion group](https://core.telegram.org/api/discussion) to associate to the channel |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type                        | Description                                                                  |
| :--: | --------------------------- | ---------------------------------------------------------------------------- |
| 400  | BROADCAST_ID_INVALID        | Broadcast ID invalid.                                                        |
| 400  | CHANNEL_INVALID             | The provided channel is invalid.                                             |
| 400  | CHAT_ADMIN_REQUIRED         | You must be an admin in this chat to do this.                                |
| 400  | LINK_NOT_MODIFIED           | Discussion link not modified.                                                |
| 400  | MEGAGROUP_ID_INVALID        | Invalid supergroup ID.                                                       |
| 400  | MEGAGROUP_PREHISTORY_HIDDEN | Group with hidden history for new members can't be set as discussion groups. |

## Can bots use this method?

No

## Related pages

#### [Discussion groups](https://core.telegram.org/api/discussion)

[Groups](https://core.telegram.org/api/channel) can be associated to a [channel](https://core.telegram.org/api/channel) as a [discussion group](https://telegram.org/blog/privacy-discussions-web-bots), to allow users to discuss about posts.
