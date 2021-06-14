**Project NewCaw** \
Author: Frederick Schenk

# Content/PostFlag

```c#
public enum PostFlag
```

Defines different states for an [`Post`](../class/Post.md).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [Tweet](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/tweet) | [Tweet](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/tweet) | [Status](https://docs.joinmastodon.org/entities/status/) |

## Values

### `DELETED`

This Post was recently deleted, but is still in Memory.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `VIEWED`

This Post was seen by the user. Used to determine where to place the viewport of the timeline viewer.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `LIKED`

This Post was liked by the active user.

| Scope        | `TwitterLegacy`    | `Twitter`                 | `Mastodon`         |
| ------------ | ------------------ | ------------------------- | ------------------ |
| Available    | ✓                  | ✓                         | ✓                  |
| API-Endpoint | `favorited` (bool) | ![No API endpoint yet][2] | `favorited` (bool) |

### `REPOSTED`

This Post was reposted by the active user.

| Scope        | `TwitterLegacy`    | `Twitter`                 | `Mastodon`         |
| ------------ | ------------------ | ------------------------- | ------------------ |
| Available    | ✓                  | ✓                         | ✓                  |
| API-Endpoint | `retweeted` (bool) | ![No API endpoint yet][2] | `reblogged` (bool) |

### `REPLIED`

This Post has an reply from the active user.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `HIDDEN_ON_TIMELINES`

This Post is set to not be shown on timelines.

| Scope        | `TwitterLegacy` | `Twitter` | `Mastodon`                          |
| ------------ | --------------- | --------- | ----------------------------------- |
| Available    | ✗               | ✗         | ✓                                   |
| API-Endpoint |                 |           | `visibility/unlisted` (string enum) |

### `HIDDEN_UNLESS_FOLLOWER`

This Post is set to be only shown to followers of the author.

> May not be neccessary, if we can only pull this posts when we actually follow a user?

| Scope        | `TwitterLegacy` | `Twitter` | `Mastodon`                         |
| ------------ | --------------- | --------- | ---------------------------------- |
| Available    | ✗               | ✗         | ✓                                  |
| API-Endpoint |                 |           | `visibility/private` (string enum) |

### `HIDDEN_UNLESS_MENTIONED`

This Post is set to be only shown if the active user was mentioned directly.

> May not be neccessary, if we can only pull this posts when we actually are mentioned?

| Scope        | `TwitterLegacy` | `Twitter` | `Mastodon`                        |
| ------------ | --------------- | --------- | --------------------------------- |
| Available    | ✗               | ✗         | ✓                                 |
| API-Endpoint |                 |           | `visibility/direct` (string enum) |

### `ONLY_FOLLOWER_REPLY`

This Post is set to only allow replies from followers of the author.

| Scope        | `TwitterLegacy` | `Twitter`                                | `Mastodon`     |
| ------------ | --------------- | ---------------------------------------- | -------------- |
| Available    | ✗               | ✓                                        | ✗              |
| API-Endpoint |                 | `reply_settings/followers` (string enum) |                |

### `ONLY_MENTIONED_REPLY`

This Post is set to only allow replies from mentioned users.

| Scope        | `TwitterLegacy` | `Twitter`                                      | `Mastodon`     |
| ------------ | --------------- | ---------------------------------------------- | -------------- |
| Available    | ✗               | ✓                                              | ✗              |
| API-Endpoint |                 | `reply_settings/mentioned_users` (string enum) |                |

### `SENSITIVE`

This Post contains content not suitable for everyone.

> Twitter seems to have two booleans here: One for media and one for links, so this is a combination of both, but listed here is the field for the link one.

| Scope        | `TwitterLegacy`             | `Twitter`                   | `Mastodon`         |
| ------------ | --------------------------- | --------------------------- | ------------------ |
| Available    | ✓                           | ✓                           | ✓                  |
| API-Endpoint | `possibly_sensitive` (bool) | `possibly_sensitive` (bool) | `sensitive` (bool) |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
