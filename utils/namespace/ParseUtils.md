**Project NewCaw** \
Author: Frederick Schenk

# Utils/ParseUtils

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public namespace ParseUtils
```

`ParseUtils` contains helper functions for parsing data from the platform to usable data for the backend.

### `format_text` {#method_format_text}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string format_text (string input, TextEntity[]? entities = null) 
```

Called to convert the text given by the API into a UI-compatible format. Used for [`text`](../../content/class/Post.md#property_text) in [`Post`](../../content/class/Post.md) and [`description`](../../content/class/User.md#property_description) in [`User`](../../content/class/User.md).

> This might be multiple functions, as there are different strings to format. Twitter provides a simple string, in which interactive entities (such as hashtags) needs to be embedded, while Mastodon provides a fully formatted HTML-string where we likely need to simplify things.

### `format_date` {#method_format_date}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square)\

```c#
public GLib.DateTime format_date (string input)
```

Called to convert the custom date format to a standard `GLib.DateTime`.
