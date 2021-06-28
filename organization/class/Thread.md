**Project NewCaw** \
Author: Frederick Schenk

# Organization/Thread

```c#
public interface Thread
```

`Thread` stores multiple [`Post`](../../content/class/Post.md) and notes if they are replies to each other, so we can display these threads later on.

Threads are created for any Post which DetailView is called, if not done already. The calling Post (called `focus` in creation methods) is center-point for determine which Posts are loaded immediately. Posts that are loaded immediately are all steps above `focus` and 2 steps below it, additionally all posts that form a thread by one author with `focus`. Posts not immediately loaded are loaded should they be required by the user.

> Twitter's v2 API does allow for querying the thread, making it easy and economical to contruct. However, Twitter's v1 API as well as Mastodon's API only provide a "replies to" field, which means we need to manually assemble the thread using this field.

| Scope                     | `TwitterLegacy`             | `Twitter`                      | `Mastodon`       |
| ------------------------- | --------------------------- | ------------------------------ | ---------------- |
| Available                 | ✓                           | ✓                              | ✓                |
| API-Endpoint "Thread"     |                             | `conversation_id`              |                  |
| API-Endpoint "Replied to" | `in_reply_to_status_id_str` | `referenced_tweets.replied_to` | `in_reply_to_id` |

## Static Methods

### `get_replies` {#static_method_get_replies}

```c#
public static Post[] get_replies (Post post)
```

Retrieves all replies to the given Post.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `get_thread` {#static_method_get_thread}

```c#
public static Post[] get_thread (Post post)
```

Retrieves all posts that forms a thread from the given start point. When the tree branches, prefer tweets where previous mentioned people reply and those which are going deeper.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Creation Methods

### `Thread.from_post` {#creation_method_from_post}

```c#
public Thread.from_post (Post post, string? conversation_id = null)
```

Takes a [`Post`](../../content/class/Post.md) and creates the Thread from it.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Fields

### `conversation_id` {#field_conversation_id}

```c#
private string? conversation_id
```

If available, we store the conversation_id so we can fetch additional posts from there.

| Scope        | `TwitterLegacy` | `Twitter`                  | `Mastodon`     |
| ------------ | --------------- | -------------------------- | -------------- |
| Available    | ✗               | ✓                          | ✗              |
| API-Endpoint |                 | `conversation_id` (string) |                |

### `thread_node` {#field_thread_node}

```c#
private GLib.Node<Post> thread_node
```

The node with the [`Post`](../content/class/Post.md) which started this Thread. Used internally to retrieve additional posts.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
