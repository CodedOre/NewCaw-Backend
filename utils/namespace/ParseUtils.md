**Project NewCaw** \
Author: Frederick Schenk

# Utils/ParseUtils

```c#
public namespace ParseUtils
```

`ParseUtils` contains helper functions for parsing data from the platform to usable data for the backend.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `format_text` {#method_format_text}

```c#
public string format_text (string input, TextEntity[]? entities = null) 
```

Called to convert the text given by the API into a UI-compatible format. Used for [`text`](../../content/class/Post.md#property_text) in [`Post`](../../content/class/Post.md) and [`description`](../../content/class/User.md#property_description) in [`User`](../../content/class/User.md).

> This might be multiple functions, as there are different strings to format. Twitter provides a simple string, in which interactive entities (such as hashtags) needs to be embedded, while Mastodon provides a fully formatted HTML-string where we likely need to simplify things.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `format_date` {#method_format_date}

```c#
public GLib.DateTime format_date (string input)
```

Called to convert the custom date format to a standard `GLib.DateTime`.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✗              | ✗              |
| API-Endpoint | ![Internal][1]  |                |                |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
