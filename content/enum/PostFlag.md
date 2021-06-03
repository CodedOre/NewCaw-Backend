**Project NewCaw** \
Author: Frederick Schenk

# Content/PostFlag

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public enum PostFlag
```

Defines different states for an [`Post`](../class/Post.md).

## Values

### `DELETED`

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

This Post was recently deleted, but is still in Memory.

### `VIEWED`

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

This Post was seen by the user. Used to determine where to place the viewport of the timeline viewer.

### `LIKED`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

This Post was liked by the active user.

| API   | Twitter 1   | Twitter 2 | Mastodon    |
| ----- | ----------- | --------- | ----------- |
| Field | `favorited` |           | `favorited` |
| Type  | bool        |           | bool        |

### `REPOSTED`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

This Post was reposted by the active user.

| API   | Twitter 1   | Twitter 2 | Mastodon    |
| ----- | ----------- | --------- | ----------- |
| Field | `retweeted` |           | `reblogged` |
| Type  | bool        |           | bool        |

### `REPLIED`

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

This Post has an reply from the active user.

### `HIDDEN_ON_TIMELINES`

![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)\

This Post is set to not be shown on timelines.

| API   | Mastodon              |
| ----- | --------------------- |
| Field | `visibility/unlisted` |
| Type  | string enum           |

### `HIDDEN_UNLESS_FOLLOWER`

![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)\

This Post is set to be only shown to followers of the author.

> May not be neccessary, if we can only pull this posts when we actually follow a user?

| API   | Mastodon             |
| ----- | -------------------- |
| Field | `visibility/private` |
| Type  | string enum          |

### `HIDDEN_UNLESS_MENTIONED`

![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)\

This Post is set to be only shown if the active user was mentioned directly.

> May not be neccessary, if we can only pull this posts when we actually are mentioned?

| API   | Mastodon            |
| ----- | --------------------|
| Field | `visibility/direct` |
| Type  | string enum         |

### `ONLY_FOLLOWER_REPLY`

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)\

This Post is set to only allow replies from followers of the author.

| API   | Twitter 2                  |
| ----- | ---------------------------|
| Field | `reply_settings/followers` |
| Type  | string enum                |

### `ONLY_MENTIONED_REPLY`

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)\

This Post is set to only allow replies from mentioned users.

| API   | Twitter 2                        |
| ----- | ---------------------------------|
| Field | `reply_settings/mentioned_users` |
| Type  | string enum                      |

### `SENSITIVE`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

This Post contains content not suitable for everyone.

> Twitter seems to have two booleans here: One for media and one for links, so this is a combination of both, but listed here is the field for the link one.

| API   | Twitter 1            | Twitter 2            | Mastodon    |
| ----- | -------------------- | -------------------- | ----------- |
| Field | `possibly_sensitive` | `possibly_sensitive` | `sensitive` |
| Type  | bool                 | bool                 | bool        |
