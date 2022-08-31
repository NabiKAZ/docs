# account.UpdateNotifySettings

Edits notification settings from a given user/group, from all users/all groups.

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
    new Api.account.UpdateNotifySettings({
      peer: "username",
      settings: new Api.InputPeerNotifySettings({
        showPreviews: false,
        muteUntil: 43,
        sound: new Api.NotificationSoundDefault({}),
      }),
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
    new Api.account.UpdateNotifySettings({
      peer: "username",
      settings: new Api.InputPeerNotifySettings({
        showPreviews: false,
        muteUntil: 43,
        sound: new Api.NotificationSoundDefault({}),
      }),
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|     Name     | Type                                                                              | Description           |
| :----------: | --------------------------------------------------------------------------------- | --------------------- |
|   **peer**   | [InputNotifyPeer](https://core.telegram.org/type/InputNotifyPeer)                 | Notification source   |
| **settings** | [InputPeerNotifySettings](https://core.telegram.org/type/InputPeerNotifySettings) | Notification settings |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type             | Description                                 |
| :--: | ---------------- | ------------------------------------------- |
| 400  | CHANNEL_INVALID  | The provided channel is invalid.            |
| 400  | CHANNEL_PRIVATE  | You haven't joined this channel/supergroup. |
| 400  | MSG_ID_INVALID   | Invalid message ID provided.                |
| 400  | PEER_ID_INVALID  | The provided peer id is invalid.            |
| 400  | SETTINGS_INVALID | Invalid settings were provided.             |

## Can bots use this method?

No

## Related pages
