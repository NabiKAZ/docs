# channels.InviteToChannel

Invite users to a channel/supergroup

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
    new Api.channels.InviteToChannel({
      channel: "username",
      users: ["username"],
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
    new Api.channels.InviteToChannel({
      channel: "username",
      users: ["username"],
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|    Name     | Type                                                                                                       | Description        |
| :---------: | ---------------------------------------------------------------------------------------------------------- | ------------------ |
| **channel** | [InputChannel](https://core.telegram.org/type/InputChannel)                                                | Channel/supergroup |
|  **users**  | [Vector](https://core.telegram.org/type/Vector%20t)<[InputUser](https://core.telegram.org/type/InputUser)> | Users to invite    |

## Result

[Updates](https://core.telegram.org/type/Updates)

## Possible errors

| Code | Type                    | Description                                                                    |
| :--: | ----------------------- | ------------------------------------------------------------------------------ |
| 400  | BOTS_TOO_MUCH           | There are too many bots in this chat/channel.                                  |
| 400  | BOT_GROUPS_BLOCKED      | This bot can't be added to groups.                                             |
| 400  | CHANNEL_INVALID         | The provided channel is invalid.                                               |
| 400  | CHANNEL_PRIVATE         | You haven't joined this channel/supergroup.                                    |
| 400  | CHAT_ADMIN_REQUIRED     | You must be an admin in this chat to do this.                                  |
| 400  | CHAT_INVALID            | Invalid chat.                                                                  |
| 403  | CHAT_WRITE_FORBIDDEN    | You can't write in this chat.                                                  |
| 400  | INPUT_USER_DEACTIVATED  | The specified user was deleted.                                                |
| 400  | MSG_ID_INVALID          | Invalid message ID provided.                                                   |
| 400  | USERS_TOO_MUCH          | The maximum number of users has been exceeded (to create a chat, for example). |
| 400  | USER_BANNED_IN_CHANNEL  | You're banned from sending messages in supergroups/channels.                   |
| 400  | USER_BLOCKED            | User blocked.                                                                  |
| 400  | USER_BOT                | Bots can only be admins in channels.                                           |
| 403  | USER_CHANNELS_TOO_MUCH  | One of the users you tried to add is already in too many channels/supergroups. |
| 400  | USER_ID_INVALID         | The provided user ID is invalid.                                               |
| 400  | USER_KICKED             | This user was kicked from this supergroup/channel.                             |
| 403  | USER_NOT_MUTUAL_CONTACT | The provided user is not a mutual contact.                                     |
| 403  | USER_PRIVACY_RESTRICTED | The user's privacy settings do not allow you to do this.                       |

## Can bots use this method?

No

## Related pages
