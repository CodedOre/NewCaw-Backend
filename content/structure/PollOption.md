**Project NewCaw** \
Author: Frederick Schenk

# Content/PollOption

```c#
public struct PollOption
```

A small helper structure for storing options in a [`Poll`](../class/Poll.md).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✗               | ✓              | ✓              |
| API-Endpoint |                 | [Poll](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/poll) | [Poll](https://docs.joinmastodon.org/entities/poll/) |

## Fields

### `title`

```c#
public string title
```

The title of this option.

| Scope        | `TwitterLegacy` | `Twitter`        | `Mastodon`       |
| ------------ | --------------- | ---------------- | ---------------- |
| Available    | ✗               | ✓                | ✓                |
| API-Endpoint |                 | `label` (string) | `title` (string) |

### `votes`

```c#
public int votes
```

How many votes this option got.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`          |
| ------------ | --------------- | -------------- | ------------------- |
| Available    | ✗               | ✓              | ✓                   |
| API-Endpoint |                 | `votes` (int)  | `votes_count` (int) |

### `user_voted`

```c#
public bool user_voted
```

True if the current user has voted for this option.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`              |
| ------------ | --------------- | ------------------------- | ----------------------- |
| Available    | ✗               | ✓                         | ✓                       |
| API-Endpoint |                 | ![No API endpoint yet][2] | `own_votes` (int array) |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
