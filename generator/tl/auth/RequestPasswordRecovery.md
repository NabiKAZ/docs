# auth.RequestPasswordRecovery

Request recovery code of a [2FA password](https://core.telegram.org/api/srp), only for accounts with a [recovery email configured](https://core.telegram.org/api/srp#email-verification).



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

    const result = await client.invoke(new Api.auth.RequestPasswordRecovery({}));
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

    const result: Api.auth.PasswordRecovery = await client.invoke(new Api.auth.RequestPasswordRecovery({}));
    console.log(result); // prints the result
})();
```
:::
::::



## Parameters

| Name | Type | Description |
| :--: | ---- | ----------- |



## Result

[auth.PasswordRecovery](https://core.telegram.org/type/auth.PasswordRecovery)



## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

| 400 | PASSWORD\_EMPTY | The provided password is empty. 
| 400 | PASSWORD\_RECOVERY\_NA | No email was set, can't recover password via email. 


## Can bots use this method?

No

## Related pages

#### [Two-factor authentication](https://core.telegram.org/api/srp)

How to login to a user's account if they have enabled 2FA, how to change password.




