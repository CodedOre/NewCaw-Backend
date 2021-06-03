**Project NewCaw** \
Author: Frederick Schenk

# Content/Poll

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public class Poll
```

`Poll` is the generic class storing a the content of an poll posted on the supported platforms.

| API    | Twitter 2 | Mastodon |
| ------ | --------- | -------- |
| Object | [Poll](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/poll) | [Poll](https://docs.joinmastodon.org/entities/poll/) |

## Properties

### `id` {#property_id}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string id { get; }
```

The unique identifier for this Poll.

| API   | Twitter 2 | Mastodon |
| ----- | --------- | -------- |
| Field | `id`      | `id`     |
| Type  | string    | string   |

### `end_date` {#property_end_date}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public GLib.Date end_date { get; }
```

The date when the poll ends.

| API   | Twitter 2       | Mastodon        |
| ----- | --------------- | --------------- |
| Field | `end_datetime`  | `expires_at`    |
| Type  | ISO 8601 string | ISO 8601 string |

### `options` {#property_options}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public PollOption[] options { get; }
```

All options this Poll contains. See [`PollOoption`](../structure/PollOption.md).

| API   | Twitter 2 | Mastodon  |
| ----- | --------- | --------- |
| Field | `options` | `options` |
| Type  | array     | array     |

## Creation Methods

### `Poll.from_json` {#creation_method_from_json}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Poll.from_json (Json.Object obj)
```

Creates a Poll Object from a given Json object.

## Methods

### `has_flag` {#method_has_flag}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public bool has_flag (PollFlag flag)
```

Returns if the Poll has a specific flag set.

### `set_flag` {#method_set_flag}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public void set_flag (PollFlag flag)
```

Sets a flag for this Poll.

### `unset_flag` {#method_unset_flag}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public void unset_flag (PollFlag flag)
```

Removes a flag from this Poll.

## Fields

### `flags` {#field_flags}

```c#
private Gee.HashSet<PollFlag> flags
```

Contains flags set for different states of an Poll. See [`PollFlag`](../enum/PollFlag.md).
