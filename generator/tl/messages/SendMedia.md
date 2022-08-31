# messages.SendMedia

Send a media

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
    new Api.messages.SendMedia({
      peer: "username",
      media: new Api.InputMediaUploadedPhoto({
        file: await client.uploadFile({
          file: new CustomFile(
            "file.bin",
            fs.statSync("../file.bin").size,
            "../file.bin"
          ),
          workers: 1,
        }),
        stickers: [
          new Api.InputDocument({
            id: BigInt("-4156887774564"),
            accessHash: BigInt("-4156887774564"),
            fileReference: Buffer.from("arbitrary data here"),
          }),
        ],
        ttlSeconds: 43,
      }),
      message: "Hello there!",
      randomId: BigInt("-4156887774564"),
      noforwards: true,
      scheduleDate: 43,
      sendAs: "username",
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
    new Api.messages.SendMedia({
      peer: "username",
      media: new Api.InputMediaUploadedPhoto({
        file: await client.uploadFile({
          file: new CustomFile(
            "file.bin",
            fs.statSync("../file.bin").size,
            "../file.bin"
          ),
          workers: 1,
        }),
        stickers: [
          new Api.InputDocument({
            id: BigInt("-4156887774564"),
            accessHash: BigInt("-4156887774564"),
            fileReference: Buffer.from("arbitrary data here"),
          }),
        ],
        ttlSeconds: 43,
      }),
      message: "Hello there!",
      randomId: BigInt("-4156887774564"),
      noforwards: true,
      scheduleDate: 43,
      sendAs: "username",
    })
  );
  console.log(result); // prints the result
})();
```

:::
::::

## Parameters

|       Name       | Type                                                                                                                                                                                              | Description                                                                                                                                                                                                 |
| :--------------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|    **flags**     | [#](https://core.telegram.org/type/%23)                                                                                                                                                           | Flags, see [TL conditional fields](https://core.telegram.org/mtproto/TL-combinators#conditional-fields)                                                                                                     |
|    **silent**    | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).5?[true](https://core.telegram.org/constructor/true)                                                                 | Send message silently (no notification should be triggered)                                                                                                                                                 |
|  **background**  | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).6?[true](https://core.telegram.org/constructor/true)                                                                 | Send message in background                                                                                                                                                                                  |
|  **clearDraft**  | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).7?[true](https://core.telegram.org/constructor/true)                                                                 | Clear the draft                                                                                                                                                                                             |
|  **noforwards**  | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).14?[true](https://core.telegram.org/constructor/true)                                                                | Only for bots, disallows forwarding and saving of the messages, even if the destination chat doesn't have [content protection](https://telegram.org/blog/protected-content-delete-by-date-and-more) enabled |
|     **peer**     | [InputPeer](https://core.telegram.org/type/InputPeer)                                                                                                                                             | Destination                                                                                                                                                                                                 |
| **replyToMsgId** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).0?[int](https://core.telegram.org/type/int)                                                                          | Message ID to which this message should reply to                                                                                                                                                            |
|    **media**     | [InputMedia](https://core.telegram.org/type/InputMedia)                                                                                                                                           | Attached media                                                                                                                                                                                              |
|   **message**    | [string](https://core.telegram.org/type/string)                                                                                                                                                   | Caption                                                                                                                                                                                                     |
|   **randomId**   | [long](https://core.telegram.org/type/long)                                                                                                                                                       | Random ID to avoid resending the same message                                                                                                                                                               |
| **replyMarkup**  | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).2?[ReplyMarkup](https://core.telegram.org/type/ReplyMarkup)                                                          | Reply markup for bot keyboards                                                                                                                                                                              |
|   **entities**   | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).3?[Vector](https://core.telegram.org/type/Vector%20t)<[MessageEntity](https://core.telegram.org/type/MessageEntity)> | Message [entities](https://core.telegram.org/api/entities) for styled text                                                                                                                                  |
| **scheduleDate** | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).10?[int](https://core.telegram.org/type/int)                                                                         | Scheduled message date for [scheduled messages](https://core.telegram.org/api/scheduled-messages)                                                                                                           |
|    **sendAs**    | [flags](https://core.telegram.org/mtproto/TL-combinators#conditional-fields).13?[InputPeer](https://core.telegram.org/type/InputPeer)                                                             | Send this message as the specified peer                                                                                                                                                                     |

## Result

[Updates](https://core.telegram.org/type/Updates)

## Possible errors

| Code | Type                              | Description                                                                                                                     |
| :--: | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| 400  | BOT_PAYMENTS_DISABLED             | Please enable bot payments in botfather before calling this method.                                                             |
| 400  | BROADCAST_PUBLIC_VOTERS_FORBIDDEN | You can't forward polls with public voters.                                                                                     |
| 400  | BUTTON_DATA_INVALID               | The data of one or more of the buttons you provided is invalid.                                                                 |
| 400  | BUTTON_TYPE_INVALID               | The type of one or more of the buttons you provided is invalid.                                                                 |
| 400  | BUTTON_URL_INVALID                | Button URL invalid.                                                                                                             |
| 400  | CHANNEL_INVALID                   | The provided channel is invalid.                                                                                                |
| 400  | CHANNEL_PRIVATE                   | You haven't joined this channel/supergroup.                                                                                     |
| 400  | CHAT_ADMIN_REQUIRED               | You must be an admin in this chat to do this.                                                                                   |
| 400  | CHAT_FORWARDS_RESTRICTED          | You can't forward messages from a protected chat.                                                                               |
| 400  | CHAT_RESTRICTED                   | You can't send messages in this chat, you were restricted.                                                                      |
| 403  | CHAT_SEND_GIFS_FORBIDDEN          | You can't send gifs in this chat.                                                                                               |
| 403  | CHAT_SEND_MEDIA_FORBIDDEN         | You can't send media in this chat.                                                                                              |
| 403  | CHAT_SEND_POLL_FORBIDDEN          | You can't send polls in this chat.                                                                                              |
| 403  | CHAT_SEND_STICKERS_FORBIDDEN      | You can't send stickers in this chat.                                                                                           |
| 403  | CHAT_WRITE_FORBIDDEN              | You can't write in this chat.                                                                                                   |
| 400  | CURRENCY_TOTAL_AMOUNT_INVALID     | The total amount of all prices is invalid.                                                                                      |
| 400  | EMOTICON_INVALID                  | The specified emoji is invalid.                                                                                                 |
| 400  | EXTERNAL_URL_INVALID              | External URL invalid.                                                                                                           |
| 400  | FILE_PARTS_INVALID                | The number of file parts is invalid.                                                                                            |
| 400  | FILE_PART_LENGTH_INVALID          | The length of a file part is invalid.                                                                                           |
| 400  | FILE_REFERENCE_EMPTY              | An empty [file reference](https://core.telegram.org/api/file_reference) was specified.                                          |
| 400  | FILE_REFERENCE_EXPIRED            | File reference expired, it must be refetched as described in [the documentation](https://core.telegram.org/api/file_reference). |
| 400  | GAME_BOT_INVALID                  | Bots can't send another bot's game.                                                                                             |
| 400  | IMAGE_PROCESS_FAILED              | Failure while processing image.                                                                                                 |
| 400  | INPUT_USER_DEACTIVATED            | The specified user was deleted.                                                                                                 |
| 400  | MD5_CHECKSUM_INVALID              | The MD5 checksums do not match.                                                                                                 |
| 400  | MEDIA_CAPTION_TOO_LONG            | The caption is too long.                                                                                                        |
| 400  | MEDIA_EMPTY                       | The provided media object is invalid.                                                                                           |
| 400  | MEDIA_INVALID                     | Media invalid.                                                                                                                  |
| 400  | MSG_ID_INVALID                    | Invalid message ID provided.                                                                                                    |
| 400  | PAYMENT_PROVIDER_INVALID          | The specified payment provider is invalid.                                                                                      |
| 400  | PEER_ID_INVALID                   | The provided peer id is invalid.                                                                                                |
| 400  | PHOTO_EXT_INVALID                 | The extension of the photo is invalid.                                                                                          |
| 400  | PHOTO_INVALID_DIMENSIONS          | The photo dimensions are invalid.                                                                                               |
| 400  | PHOTO_SAVE_FILE_INVALID           | Internal issues, try again later.                                                                                               |
| 400  | POLL_ANSWERS_INVALID              | Invalid poll answers were provided.                                                                                             |
| 400  | POLL_ANSWER_INVALID               | One of the poll answers is not acceptable.                                                                                      |
| 400  | POLL_OPTION_DUPLICATE             | Duplicate poll options provided.                                                                                                |
| 400  | POLL_OPTION_INVALID               | Invalid poll option provided.                                                                                                   |
| 400  | POLL_QUESTION_INVALID             | One of the poll questions is not acceptable.                                                                                    |
| 400  | QUIZ_CORRECT_ANSWERS_EMPTY        | No correct quiz answer was specified.                                                                                           |
| 400  | QUIZ_CORRECT_ANSWERS_TOO_MUCH     | You specified too many correct answers in a quiz, quizzes can only have one right answer!                                       |
| 400  | QUIZ_CORRECT_ANSWER_INVALID       | An invalid value was provided to the correct_answers field.                                                                     |
| 400  | QUIZ_MULTIPLE_INVALID             | Quizzes can't have the multiple_choice flag set!                                                                                |
| 500  | RANDOM_ID_DUPLICATE               | You provided a random ID that was already used.                                                                                 |
| 400  | REPLY_MARKUP_BUY_EMPTY            | Reply markup for buy button empty.                                                                                              |
| 400  | REPLY_MARKUP_INVALID              | The provided reply markup is invalid.                                                                                           |
| 400  | SCHEDULE_BOT_NOT_ALLOWED          | Bots cannot schedule messages.                                                                                                  |
| 400  | SCHEDULE_DATE_TOO_LATE            | You can't schedule a message this far in the future.                                                                            |
| 400  | SCHEDULE_TOO_MUCH                 | There are too many scheduled messages.                                                                                          |
| 400  | SEND_AS_PEER_INVALID              | You can't send messages as the specified peer.                                                                                  |
| 420  | SLOWMODE_WAIT\_%d                 | Slowmode is enabled in this chat: wait %d seconds before sending another message to this chat.                                  |
| 400  | TTL_MEDIA_INVALID                 | Invalid media Time To Live was provided.                                                                                        |
| 400  | USER_BANNED_IN_CHANNEL            | You're banned from sending messages in supergroups/channels.                                                                    |
| 403  | USER_IS_BLOCKED                   | You were blocked by this user.                                                                                                  |
| 400  | USER_IS_BOT                       | Bots can't send messages to other bots.                                                                                         |
| 400  | VIDEO_CONTENT_TYPE_INVALID        | The video's content type is invalid.                                                                                            |
| 400  | WEBPAGE_CURL_FAILED               | Failure while fetching the webpage with cURL.                                                                                   |
| 400  | WEBPAGE_MEDIA_EMPTY               | Webpage media empty.                                                                                                            |
| 400  | YOU_BLOCKED_USER                  | You blocked this user.                                                                                                          |

## Can bots use this method?

Yes

## Related pages

#### [Styled text with message entities](https://core.telegram.org/api/entities)

How to create styled text with message entities

#### [Scheduled messages](https://core.telegram.org/api/scheduled-messages)

Telegram allows scheduling messages

#### [File references](https://core.telegram.org/api/file_reference)

How to handle file references.
