**Project NewCaw** \
Author: Frederick Schenk

# Content/TextEntity

```c#
public struct TextEntity
```

`TextEntity` stores information about special entities (like mentions or hashtags) that can be found in a text.

> `TextEntity` stores different kinds of entities, such as hashtags, urls and mentions, and provides standardized links for the frontend to perform wanted actions when selected. As the API endpoints are quite different between those entities we do not note them here.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [Entities](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/entities) | Entities | ![Internal][1] |

## Fields

### `display_text`

```c#
public string display_text
```

The string that is displayed in the string.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |

### `text_start`

```c#
public uint text_start
```

The point where the entity starts in the text.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |

### `text_end`

```c#
public uint text_end
```

The point where the entity stops in the text.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |

### `full_text`

```c#
public string full_text
```

The string of the complete text of the entity. Used for the tooltip as well.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
