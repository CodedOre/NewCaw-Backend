**Project NewCaw** \
Author: Frederick Schenk

# Content/User

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface User
```

`User` is the generic class storing a user who does something on a platform.

| API    | Twitter 1 | Twitter 2 | Mastodon |
| ------ | --------- | --------- | -------- |
| Object | [User](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/user) | [User](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user) | [Account](https://docs.joinmastodon.org/entities/account/) |

## Properties

### `id` {#property_id}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string id { get; }
```

The unique identifier of a user.

| API   | Twitter 1 | Twitter 2 | Mastodon |
| ----- | --------- | --------- | -------- |
| Field | `id_str`  | `id`      | `id`     |
| Type  | string    | string    | string   |

### `display_name` {#property_display_name}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string display_name { get; }
```

The "name" of a user.

| API   | Twitter 1 | Twitter 2 | Mastodon       |
| ----- | --------- | --------- | -------------- |
| Field | `name`    | `name`    | `display_name` |
| Type  | string    | string    | string         |

### `username` {#property_username}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string username { get; }
```

The unique handle of a user to identify it on the platform.

| API   | Twitter 1     | Twitter 2  | Mastodon |
| ----- | ------------- | ---------- | -------- |
| Field | `screen_name` | `username` | `acct`   |
| Type  | string        | string     | string   |

### `avatar` {#property_avatar}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Picture avatar { get; }
```

The profile picture of the User, stored as a [`Picture`](Picture.md).

> Mastodon provides the option to use a animated GIF (which we store as a [`Animated`](Animated.md)) as a avatar. For now, we will not consider this option as it makes the code more complex and use always the static variant.

| API   | Twitter 1                 | Twitter 2           | Mastodon        |
| ----- | ------------------------- | ------------------- | --------------- |
| Field | `profile_image_url_https` | `profile_image_url` | `avatar_static` |
| Type  | url string                | url string          | url string      |

## Creation Methods

### `User.from_json` {#creation_method_from_json}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public User.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

## Methods

### `has_flag` {#method_has_flag}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public bool has_flag (UserFlag flag)
```

Returns if the User has a specific flag set.

### `set_flag` {#method_set_flag}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public void set_flag (UserFlag flag)
```

Sets a flag for this User.

### `unset_flag` {#method_unset_flag}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public void unset_flag (UserFlag flag)
```

Removes a flag from this User.

## Fields

### `flags` {#field_flags}

```c#
private Gee.HashSet<UserFlag> flags
```

Contains flags set for different states of an User. See [`UserFlag`](../enum/UserFlag.md).
