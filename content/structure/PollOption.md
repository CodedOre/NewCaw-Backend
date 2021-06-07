**Project NewCaw** \
Author: Frederick Schenk

# Content/PollOption

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public struct PollOption
```

A small helper structure for storing options in a [`Poll`](../class/Poll.md).

## Fields

### `title`

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string title
```

The title of this option.

| API   | Twitter 2 | Mastodon |
| ----- | --------- | -------- |
| Field | `label`   | `title`  |
| Type  | string    | string   |

### `votes`

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public int votes
```

How many votes this option got.

| API   | Twitter 2 | Mastodon      |
| ----- | --------- | ------------- |
| Field | `votes`   | `votes_count` |
| Type  | int       | int           |

### `user_voted`

![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public bool user_voted
```

True if the current user has voted for this option.

| API   | Twitter 2 | Mastodon    |
| ----- | --------- | ----------- |
| Field |           | `own_votes` |
| Type  |           | int array   |
