**Project NewCaw** \
Author: Frederick Schenk

# Content/UserFlag

```c#
public enum UserFlag
```

Some flags for [`User`](../class/User.md) for different scenarios.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [User](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/user) | [User](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user) | [Account](https://docs.joinmastodon.org/entities/account/) |

## `VERIFIED`

Set if the User is verified by the platform.

| Scope        | `TwitterLegacy`   | `Twitter`         | `Mastodon`     |
| ------------ | ----------------- | ----------------- | -------------- |
| Available    | ✓                 | ✓                 | ✗              |
| API-Endpoint | `verified` (bool) | `verified` (bool) |                |

## `PROTECTED`

Set if the User moderates it's followers.

> On Twitter, this also set's if Tweets are visible to non-followers, however, this does not apply to Mastodon, where visibility of Toots is set for each seperatly.

| Scope        | `TwitterLegacy`    | `Twitter`          | `Mastodon`      |
| ------------ | ------------------ | ------------------ | --------------- |
| Available    | ✓                  | ✓                  | ✓               |
| API-Endpoint | `protected` (bool) | `protected` (bool) | `locked` (bool) |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
