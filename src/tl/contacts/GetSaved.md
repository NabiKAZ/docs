# contacts.GetSaved

Get saved GIFs



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

    const result = await client.invoke(new Api.contacts.GetSaved({}));
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

    const result: Api.Vector<SavedContact> = await client.invoke(new Api.contacts.GetSaved({}));
    console.log(result); // prints the result
})();
```
:::
::::



## Parameters

| Name | Type | Description |
| :--: | ---- | ----------- |

| **hash** | [long](https://core.telegram.org/type/long) | [Hash for pagination, for more info click here](https://core.telegram.org/api/offsets#hash-generation) 


## Result

[messages.SavedGifs](https://core.telegram.org/type/messages.SavedGifs)



## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |



## Can bots use this method?

No

## Related pages

#### [Pagination in the API](https://core.telegram.org/api/offsets)

How to fetch results from large lists of objects.




