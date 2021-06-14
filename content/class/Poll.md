**Project NewCaw** \
Author: Frederick Schenk

# Content/Poll

```c#
public class Poll
```

`Poll` is the generic class storing a the content of an poll posted on the supported platforms.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | [Poll](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/poll) | [Poll](https://docs.joinmastodon.org/entities/poll/) |

## Properties

### `id` {#property_id}

```c#
public string id { get; }
```

The unique identifier for this Poll.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | `id` (string)  | `id` (string)  |

### `end_date` {#property_end_date}

```c#
public GLib.Date end_date { get; }
```

The date when the poll ends.

| Scope        | `TwitterLegacy` | `Twitter`                        | `Mastodon`                     |
| ------------ | --------------- | -------------------------------- | ------------------------------ |
| Available    | ✗               | ✓                                | ✓                              |
| API-Endpoint |                 | `end_datetime` (ISO 8601 string) | `expires_at` (ISO 8601 string) |

### `options` {#property_options}

```c#
public PollOption[] options { get; }
```

All options this Poll contains. See [`PollOoption`](../structure/PollOption.md).

| Scope        | `TwitterLegacy` | `Twitter`         | `Mastodon`        |
| ------------ | --------------- | ----------------- | ----------------- |
| Available    | ✗               | ✓                 | ✓                 |
| API-Endpoint |                 | `options` (array) | `options` (array) |

## Creation Methods

### `Poll.from_json` {#creation_method_from_json}

```c#
public Poll.from_json (Json.Object obj)
```

Creates a Poll Object from a given Json object.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | ![Internal][1] | ![Internal][1] |

## Methods

### `has_flag` {#method_has_flag}

```c#
public bool has_flag (PollFlag flag)
```

Returns if the Poll has a specific flag set.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | ![Internal][1] | ![Internal][1] |

### `set_flag` {#method_set_flag}

```c#
public void set_flag (PollFlag flag)
```

Sets a flag for this Poll.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | ![Internal][1] | ![Internal][1] |

### `unset_flag` {#method_unset_flag}

```c#
public void unset_flag (PollFlag flag)
```

Removes a flag from this Poll.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | ![Internal][1] | ![Internal][1] |

## Fields

### `flags` {#field_flags}

```c#
private PollFlag flags
```

Contains flags set for different states of an Poll. See [`PollFlag`](../enum/PollFlag.md).

> This fields work with an [Flag enum](https://wiki.gnome.org/Projects/Vala/Manual/Enumerated%20types%20(Enums)#Flag_types).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | ![Internal][1] | ![Internal][1] |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
