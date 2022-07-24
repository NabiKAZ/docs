# messages.SetEncryptedTyping

Send typing event by the current user to a secret chat.



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

    const result = await client.invoke(new Api.messages.SetEncryptedTyping({
    peer: new Api.InputEncryptedChat({
        chatId: 43,
        accessHash: BigInt('-4156887774564')
    }),
    typing: false
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

    const result: Api.Bool = await client.invoke(new Api.messages.SetEncryptedTyping({
    peer: new Api.InputEncryptedChat({
        chatId: 43,
        accessHash: BigInt('-4156887774564')
    }),
    typing: false
}));
    console.log(result); // prints the result
})();
```
:::
::::



## Parameters

| Name | Type | Description |
| :--: | ---- | ----------- |

| **peer** | [InputEncryptedChat](https://core.telegram.org/type/InputEncryptedChat) | Secret chat ID 
| **typing** | [Bool](https://core.telegram.org/type/Bool) | Typing.**Possible values**:[(boolTrue)](https://core.telegram.org/constructor/boolTrue), if the user started typing and more than **5 seconds** have passed since the last request[(boolFalse)](https://core.telegram.org/constructor/boolFalse), if the user stopped typing 


## Result

[Bool](https://core.telegram.org/type/Bool)



## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

| 400 | CHAT\_ID\_INVALID | The provided chat id is invalid. 


## Can bots use this method?

No

## Related pages

#### [boolTrue](https://core.telegram.org/constructor/boolTrue)

The constructor can be interpreted as a \*\*boolean\*\*`true` value.



#### [boolFalse](https://core.telegram.org/constructor/boolFalse)

Constructor may be interpreted as a \*\*boolean\*\*`false` value.




