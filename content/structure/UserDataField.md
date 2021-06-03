**Project NewCaw** \
Author: Frederick Schenk

# Content/UserDataField

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public structure UserDataField
```

`UserDataField` stores additional information a [`User`](../class/User.md) has set.

> This structure is neccessary for Mastodon, as the user is free to create as much fields as he likes. However, for Twitter there are only two static fields, `location` and `url`, which are stored as a `UserDataField` for consistency.
>
> Therefore Mastodon has a own specification for fields, where on Twitter we only populate this with two string from other fields.

| API    | Mastodon |
| ------ | -------- |
| Object | [Field](https://docs.joinmastodon.org/entities/field/) |

## Fields

### `name`

```c#
public string name
```

The key for the field.

| API   | Mastodon |
| ----- | -------- |
| Field | `name`   |
| Type  | string   |

### `value`

```c#
public string value
```

The value of the field.

| API   | Mastodon |
| ----- | -------- |
| Field | `value`  |
| Type  | string   |
