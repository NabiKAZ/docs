# messages.SendMessage

Sends a message to a chat



## Example

::::tabs
:::tab{title="JavaScript"}
```js
const {Api, TelegramClient} = require('telegram');
const {StringSession} = require('telegram/sessions');

const session = new StringSession(''); // You should put your string session here
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
    await client.connect() // This assumes you have already authenticated with .start()

    const result = await client.invoke(new Api.messages.SendMessage({
    peer: 'username',
    message: 'Hello there!',
    randomId: BigInt('-4156887774564'),
    noWebpage: true,
    noforwards: true,
    updateStickersetsOrder: true,
    replyTo: new Api.InputReplyToMessage({
        replyToMsgId: 43,
        topMsgId: 43
    }),
    scheduleDate: 43,
    sendAs: 'username'
}));
    console.log(result); // prints the result
})();
```
:::

:::tab{title="TypeScript"}
```ts
import {Api, TelegramClient} from 'telegram';
import {StringSession} from 'telegram/sessions';

const session = new StringSession(''); // You should put your string session here
const client = new TelegramClient(session, apiId, apiHash, {});

(async function run() {
    await client.connect() // This assumes you have already authenticated with .start()

    const result: Api.Updates = await client.invoke(new Api.messages.SendMessage({
    peer: 'username',
    message: 'Hello there!',
    randomId: BigInt('-4156887774564'),
    noWebpage: true,
    noforwards: true,
    updateStickersetsOrder: true,
    replyTo: new Api.InputReplyToMessage({
        replyToMsgId: 43,
        topMsgId: 43
    }),
    scheduleDate: 43,
    sendAs: 'username'
}));
    console.log(result); // prints the result
})();
```
:::
::::



## Parameters

| Name | Type | Description |
| :--: | ---- | ----------- |

| **flags** | [#](https://core.telegram.org/type/%23) | Flags, see [TL conditional fields](https://core.telegram.org/mtproto/TL-combinators#conditional-fields) 
| **noWebpage** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).1?[true](https://core.telegram.org/constructor/true) | Set this flag to disable generation of the webpage preview 
| **silent** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).5?[true](https://core.telegram.org/constructor/true) | Send this message silently (no notifications for the receivers) 
| **background** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).6?[true](https://core.telegram.org/constructor/true) | Send this message as background message 
| **clearDraft** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).7?[true](https://core.telegram.org/constructor/true) | Clear the draft field 
| **noforwards** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).14?[true](https://core.telegram.org/constructor/true) | Only for bots, disallows forwarding and saving of the messages, even if the destination chat doesn't have [content protection](https://telegram.org/blog/protected-content-delete-by-date-and-more) enabled 
| **peer** | [InputPeer](https://core.telegram.org/type/InputPeer) | The destination where the message will be sent 
| **replyToMsgId** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).0?[int](https://core.telegram.org/type/int) | The message ID to which this message will reply to 
| **message** | [string](https://core.telegram.org/type/string) | The message 
| **randomId** | [long](https://core.telegram.org/type/long) | Unique client message ID required to prevent message resending 
| **replyMarkup** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).2?[ReplyMarkup](https://core.telegram.org/type/ReplyMarkup) | Reply markup for sending bot buttons 
| **entities** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).3?[Vector](https://core.telegram.org/type/Vector%20t)<[MessageEntity](https://core.telegram.org/type/MessageEntity)> | Message [entities](https://core.telegram.org/api/entities) for sending styled text 
| **scheduleDate** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).10?[int](https://core.telegram.org/type/int) | Scheduled message date for [scheduled messages](https://core.telegram.org/api/scheduled-messages) 
| **sendAs** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).13?[InputPeer](https://core.telegram.org/type/InputPeer) | Send this message as the specified peer 


## Result

[Updates](https://core.telegram.org/type/Updates)



## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

| 400 | BOT\_DOMAIN\_INVALID | Bot domain invalid. 
| 400 | BOT\_INVALID | This is not a valid bot. 
| 400 | BUTTON\_DATA\_INVALID | The data of one or more of the buttons you provided is invalid. 
| 400 | BUTTON\_TYPE\_INVALID | The type of one or more of the buttons you provided is invalid. 
| 400 | BUTTON\_URL\_INVALID | Button URL invalid. 
| 400 | CHANNEL\_INVALID | The provided channel is invalid. 
| 400 | CHANNEL\_PRIVATE | You haven't joined this channel/supergroup. 
| 400 | CHAT\_ADMIN\_REQUIRED | You must be an admin in this chat to do this. 
| 400 | CHAT\_ID\_INVALID | The provided chat id is invalid. 
| 400 | CHAT\_RESTRICTED | You can't send messages in this chat, you were restricted. 
| 403 | CHAT\_WRITE\_FORBIDDEN | You can't write in this chat. 
| 400 | ENCRYPTION\_DECLINED | The secret chat was declined. 
| 400 | ENTITIES\_TOO\_LONG | You provided too many styled message entities. 
| 400 | ENTITY\_MENTION\_USER\_INVALID | You mentioned an invalid user. 
| 400 | FROM\_MESSAGE\_BOT\_DISABLED | Bots can't use fromMessage min constructors. 
| 400 | INPUT\_USER\_DEACTIVATED | The specified user was deleted. 
| 400 | MESSAGE\_EMPTY | The provided message is empty. 
| 400 | MESSAGE\_TOO\_LONG | The provided message is too long. 
| 400 | MSG\_ID\_INVALID | Invalid message ID provided. 
| 400 | PEER\_ID\_INVALID | The provided peer id is invalid. 
| 400 | PINNED\_DIALOGS\_TOO\_MUCH | Too many pinned dialogs. 
| 400 | POLL\_OPTION\_INVALID | Invalid poll option provided. 
| 500 | RANDOM\_ID\_DUPLICATE | You provided a random ID that was already used. 
| 400 | REPLY\_MARKUP\_INVALID | The provided reply markup is invalid. 
| 400 | REPLY\_MARKUP\_TOO\_LONG | The specified reply\_markup is too long. 
| 400 | SCHEDULE\_BOT\_NOT\_ALLOWED | Bots cannot schedule messages. 
| 400 | SCHEDULE\_DATE\_TOO\_LATE | You can't schedule a message this far in the future. 
| 400 | SCHEDULE\_STATUS\_PRIVATE | Can't schedule until user is online, if the user's last seen timestamp is hidden by their privacy settings. 
| 400 | SCHEDULE\_TOO\_MUCH | There are too many scheduled messages. 
| 400 | SEND\_AS\_PEER\_INVALID | You can't send messages as the specified peer. 
| 420 | SLOWMODE\_WAIT\_%d | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat. 
| 400 | USER\_BANNED\_IN\_CHANNEL | You're banned from sending messages in supergroups/channels. 
| 403 | USER\_IS\_BLOCKED | You were blocked by this user. 
| 400 | USER\_IS\_BOT | Bots can't send messages to other bots. 
| 400 | YOU\_BLOCKED\_USER | You blocked this user. 


## Can bots use this method?

Yes

## Related pages

#### [Styled text with message entities](https://core.telegram.org/api/entities)

How to create styled text with message entities



#### [Scheduled messages](https://core.telegram.org/api/scheduled-messages)

Telegram allows scheduling messages




