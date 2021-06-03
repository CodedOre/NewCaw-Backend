**Project NewCaw** \
Author: Frederick Schenk

# Content/UserFlag

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public enum UserFlag
```

Some flags for [`User`](../class/User.md) for different scenarios.

## `VERIFIED`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)

Set if the User is verified by the platform.

| API   | Twitter 1  | Twitter 2  |
| ----- | ---------- | ---------- |
| Field | `verified` | `verified` |
| Type  | bool       | bool       |

## `PROTECTED`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

Set if the User moderates it's followers.

> On Twitter, this also set's if Tweets are visible to non-followers, however, this does not apply to Mastodon, where visibility of Toots is set for each seperatly.

| API   | Twitter 1   | Twitter 2   | Mastodon |
| ----- | ----------- | ----------- | -------- |
| Field | `protected` | `protected` | `locked` |
| Type  | bool        | bool        | bool     |
