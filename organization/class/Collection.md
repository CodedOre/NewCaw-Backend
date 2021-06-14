**Project NewCaw** \
Author: Frederick Schenk

# Organization/Collection

```c#
public interface Collection
```

`Collection` is a interface which provides basic elements which are shared by [`Timeline`](Timeline.md), [`Mentions`](Mentions.md) and [`List`](List.md).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Properties

### `last_viewed_post` {#property_last_viewed_post}

```c#
public string last_viewed_post { get; set; }
```

The id of the lastest post that was viewed by the user. Setable by the frontend.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Methods

### `get_posts` {#method_get_posts}

```c#
public Post[] get_posts ()
```

Returns [`post_list`](#field_post_list) to the caller.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `get_new_posts` {#method_get_new_posts}

```c#
public abstract Post[] get_new_posts ()
```

Calls the API to load new posts and returns them.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Fields

### `post_list` {#field_post_list}

```c#
private Post[] post_list
```

Contains references to all posts in chronological order.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `last_pulled_post` {#field_last_pulled_post}

```c#
private string last_pulled_post
```

The id of the post that has been loaded. Used to determine to which point [`get_new_posts`](#method_get_new_posts) calls new posts.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
