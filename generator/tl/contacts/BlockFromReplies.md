# contacts.BlockFromReplies

Stop getting notifications about [thread replies](https://core.telegram.org/api/threads) of a certain user in `@replies`



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

    const result = await client.invoke(new Api.contacts.BlockFromReplies({
    msgId: 43,
    deleteMessage: true,
    deleteHistory: true,
    reportSpam: true
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

    const result: Api.Updates = await client.invoke(new Api.contacts.BlockFromReplies({
    msgId: 43,
    deleteMessage: true,
    deleteHistory: true,
    reportSpam: true
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
| **deleteMessage** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).0?[true](https://core.telegram.org/constructor/true) | Whether to delete the specified message as well 
| **deleteHistory** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).1?[true](https://core.telegram.org/constructor/true) | Whether to delete all `@replies` messages from this user as well 
| **reportSpam** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).2?[true](https://core.telegram.org/constructor/true) | Whether to also report this user for spam 
| **msgId** | [int](https://core.telegram.org/type/int) | ID of the message in the [@replies](https://core.telegram.org/api/threads#replies) chat 


## Result

[Updates](https://core.telegram.org/type/Updates)



## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |



## Can bots use this method?

No

## Related pages

#### [Threads](https://core.telegram.org/api/threads)

Telegram allows commenting on a [channel post](https://core.telegram.org/api/channel) or on a generic [supergroup message](https://core.telegram.org/api/channel), thanks to message threads.




