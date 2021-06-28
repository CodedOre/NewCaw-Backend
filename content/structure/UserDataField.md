**Project NewCaw** \
Author: Frederick Schenk

# Content/UserDataField

```c#
public structure UserDataField
```

`UserDataField` stores additional information a [`User`](../class/User.md) has set.

> This structure is neccessary for Mastodon, as the user is free to create as much fields as he likes. However, for Twitter there are only two static fields, `location` and `url`, which are stored as a `UserDataField` for consistency.
>
> Therefore Mastodon has a own specification for fields, where on Twitter we only populate this with two string from other fields.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | [Field](https://docs.joinmastodon.org/entities/field/) |

## Fields

### `name`

```c#
public string name
```

The key for the field.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`      |
| ------------ | --------------- | -------------- | --------------- |
| Available    | ✓               | ✓              | ✓               |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | `name` (string) |

### `value`

```c#
public string value
```

The value of the field.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`       |
| ------------ | --------------- | -------------- | ---------------- |
| Available    | ✓               | ✓              | ✓                |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | `value` (string) |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
