# channels.JoinChannel

Join a channel/supergroup



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

    const result = await client.invoke(new Api.channels.JoinChannel({
    channel: 'username'
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

    const result: Api.Updates = await client.invoke(new Api.channels.JoinChannel({
    channel: 'username'
}));
    console.log(result); // prints the result
})();
```
:::
::::



## Parameters

| Name | Type | Description |
| :--: | ---- | ----------- |

| **channel** | [InputChannel](https://core.telegram.org/type/InputChannel) | Channel/supergroup to join 


## Result

[Updates](https://core.telegram.org/type/Updates)



## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

| 400 | CHANNELS\_TOO\_MUCH | You have joined too many channels/supergroups. 
| 400 | CHANNEL\_INVALID | The provided channel is invalid. 
| 400 | CHANNEL\_PRIVATE | You haven't joined this channel/supergroup. 
| 400 | CHAT\_INVALID | Invalid chat. 
| 400 | INVITE\_HASH\_EMPTY | The invite hash is empty. 
| 406 | INVITE\_HASH\_EXPIRED | The invite link has expired. 
| 400 | INVITE\_HASH\_INVALID | The invite hash is invalid. 
| 400 | INVITE\_REQUEST\_SENT | You have successfully requested to join this chat or channel. 
| 400 | MSG\_ID\_INVALID | Invalid message ID provided. 
| 400 | PEER\_ID\_INVALID | The provided peer id is invalid. 
| 400 | USERS\_TOO\_MUCH | The maximum number of users has been exceeded (to create a chat, for example). 
| 400 | USER\_ALREADY\_PARTICIPANT | The user is already in the group. 
| 400 | USER\_CHANNELS\_TOO\_MUCH | One of the users you tried to add is already in too many channels/supergroups. 


## Can bots use this method?

No

## Related pages


