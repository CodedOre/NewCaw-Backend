**Project NewCaw** \
Author: Frederick Schenk

# Content/User

```c#
public interface User
```

`User` is the generic class storing a user who does something on a platform.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [User](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/user) | [User](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user) | [Account](https://docs.joinmastodon.org/entities/account/) |

## Properties

### `id` {#property_id}

```c#
public string id { get; }
```

The unique identifier of a user.

| Scope        | `TwitterLegacy`   | `Twitter`      | `Mastodon`     |
| ------------ | ----------------- | -------------- | -------------- |
| Available    | ✓                 | ✓              | ✓              |
| API-Endpoint | `id_str` (string) | `id` (string)  | `id` (string)  |

### `display_name` {#property_display_name}

```c#
public string display_name { get; }
```

The "name" of a user.

| Scope        | `TwitterLegacy` | `Twitter`       | `Mastodon`              |
| ------------ | --------------- | --------------- | ----------------------- |
| Available    | ✓               | ✓               | ✓                       |
| API-Endpoint | `name` (string) | `name` (string) | `display_name` (string) |

### `username` {#property_username}

```c#
public string username { get; }
```

The unique handle of a user to identify it on the platform.

| Scope        | `TwitterLegacy`        | `Twitter`           | `Mastodon`      |
| ------------ | ---------------------- | ------------------- | --------------- |
| Available    | ✓                      | ✓                   | ✓               |
| API-Endpoint | `screen_name` (string) | `username` (string) | `acct` (string) |

### `avatar` {#property_avatar}

```c#
public Picture avatar { get; }
```

The profile picture of the User, stored as a [`Picture`](Picture.md).

> Mastodon provides the option to use a animated GIF (which we store as a [`Animated`](Animated.md)) as a avatar. For now, we will not consider this option as it makes the code more complex and use always the static variant.

| Scope        | `TwitterLegacy`                    | `Twitter`                    | `Mastodon`               |
| ------------ | ---------------------------------- | ---------------------------- | ------------------------ |
| Available    | ✓                                  | ✓                            | ✓                        |
| API-Endpoint | `profile_image_url_https` (string) | `profile_image_url` (string) | `avatar_static` (string) |

## Creation Methods

### `User.from_json` {#creation_method_from_json}

```c#
public User.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Methods

### `has_flag` {#method_has_flag}

```c#
public bool has_flag (UserFlag flag)
```

Returns if the User has a specific flag set.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `set_flag` {#method_set_flag}

```c#
public void set_flag (UserFlag flag)
```

Sets a flag for this User.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `unset_flag` {#method_unset_flag}

```c#
public void unset_flag (UserFlag flag)
```

Removes a flag from this User.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Fields

### `flags` {#field_flags}

```c#
private UserFlag flags
```

Contains flags set for different states of an User. See [`UserFlag`](../enum/UserFlag.md).

> This fields work with an [Flag enum](https://wiki.gnome.org/Projects/Vala/Manual/Enumerated%20types%20(Enums)#Flag_types).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
