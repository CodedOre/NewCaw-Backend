**Project NewCaw** \
Author: Frederick Schenk

# Content/TextEntity

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)

```c#
public struct TextEntity
```

`TextEntity` stores information about special entities (like mentions or hashtags) that can be found in a text.

> This is only relevant for the Twitter API, as Mastodon provides an HTML-string where we can probably just replace the entity-links with our values.

| API    | Twitter 1 | Twitter 2 |
| ------ | --------- | --------- |
| Object | [Entities](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/entities) |  |

## Fields

### `display_text`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)

```c#
public string display_text
```

The string that is displayed in the string.

### `text_start`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)

```c#
public uint text_start
```

The point where the entity starts in the text.

### `text_end`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)

```c#
public uint text_end
```

The point where the entity stops in the text.

### `full_text`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)

```c#
public string full_text
```

The string of the complete text of the entity. Used for the tooltip as well.
