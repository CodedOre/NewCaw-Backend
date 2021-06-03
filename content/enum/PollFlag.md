**Project NewCaw** \
Author: Frederick Schenk

# Content/PollFlag

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public enum PollFlag
```

Some flags for [`Poll`](../class/Poll.md) for different scenarios.

## `CLOSED`

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

This Poll is closed and can't recieve additional votes.

| API   | Twitter 2       | Mastodon  |
| ----- | --------------- | --------- |
| Field | `voting_status` | `expired` |
| Type  | string (why?)   | bool      |

## `MULTIPLE`

![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)\

This Poll accepts multiple choice as votes.

| API   | Mastodon   |
| ----- | ---------- |
| Field | `multiple` |
| Type  | bool       |
