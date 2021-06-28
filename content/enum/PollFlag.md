**Project NewCaw** \
Author: Frederick Schenk

# Content/PollFlag

```c#
public enum PollFlag
```

Some flags for [`Poll`](../class/Poll.md) for different scenarios.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | [Poll](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/poll) | [Poll](https://docs.joinmastodon.org/entities/poll/) |

## `CLOSED`

This Poll is closed and can't recieve additional votes.

| Scope        | `TwitterLegacy` | `Twitter`                | `Mastodon`       |
| ------------ | --------------- | ------------------------ | ---------------- |
| Available    | ✗               | ✓                        | ✓                |
| API-Endpoint |                 | `voting_status` (string) | `expired` (bool) |

## `MULTIPLE`

This Poll accepts multiple choice as votes.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`        |
| ------------ | --------------- | -------------- | ----------------- |
| Available    | ✗               | ✗              | ✓                 |
| API-Endpoint |                 |                | `multiple` (bool) |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
