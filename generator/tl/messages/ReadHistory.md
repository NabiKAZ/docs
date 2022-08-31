# messages.ReadHistory

Mark [channel/supergroup](https://core.telegram.org/api/channel) history as read

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
    new Api.messages.ReadHistory({
      peer: "username",
      maxId: 0,
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

  const result: Api.messages.AffectedMessages = await client.invoke(
    new Api.messages.ReadHistory({
      peer: "username",
      maxId: 0,
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|    Name     | Type                                                        | Description                                                 |
| :---------: | ----------------------------------------------------------- | ----------------------------------------------------------- |
| **channel** | [InputChannel](https://core.telegram.org/type/InputChannel) | [Channel/supergroup](https://core.telegram.org/api/channel) |
|  **maxId**  | [int](https://core.telegram.org/type/int)                   | ID of message up to which messages should be marked as read |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type            | Description                                 |
| :--: | --------------- | ------------------------------------------- |
| 400  | CHANNEL_INVALID | The provided channel is invalid.            |
| 400  | CHANNEL_PRIVATE | You haven't joined this channel/supergroup. |
| 400  | MSG_ID_INVALID  | Invalid message ID provided.                |

## Can bots use this method?

No

## Related pages

#### [Channels, supergroups, gigagroups and basic groups](https://core.telegram.org/api/channel)

How to handle channels, supergroups, gigagroups, basic groups, and what's the difference between them.
