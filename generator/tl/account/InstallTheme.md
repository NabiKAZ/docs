# account.InstallTheme

Install a theme

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
    new Api.account.InstallTheme({
      dark: true,
      theme: new Api.InputTheme({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      format: "some string here",
      baseTheme: new Api.BaseThemeClassic({}),
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
    new Api.account.InstallTheme({
      dark: true,
      theme: new Api.InputTheme({
        id: BigInt("-4156887774564"),
        accessHash: BigInt("-4156887774564"),
      }),
      format: "some string here",
      baseTheme: new Api.BaseThemeClassic({}),
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|     Name      | Type                                                                                                                                   | Description                                                                                             |
| :-----------: | -------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
|   **flags**   | [#](https://core.telegram.org/type/%23)                                                                                                | Flags, see [TL conditional fields](https://core.telegram.org/mtproto/TL-combinators#conditional-fields) |
|   **dark**    | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).0?[true](https://core.telegram.org/constructor/true)      | Whether to install the dark version                                                                     |
|   **theme**   | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).1?[InputTheme](https://core.telegram.org/type/InputTheme) | Theme to install                                                                                        |
|  **format**   | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).2?[string](https://core.telegram.org/type/string)         | Theme format, a string that identifies the theming engines supported by the client                      |
| **baseTheme** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).3?[BaseTheme](https://core.telegram.org/type/BaseTheme)   | Indicates a basic theme provided by all clients                                                         |

## Result

[Bool](https://core.telegram.org/type/Bool)

## Possible errors

| Code | Type | Description |
| :--: | ---- | ----------- |

## Can bots use this method?

No

## Related pages
