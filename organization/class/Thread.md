**Project NewCaw** \
Author: Frederick Schenk

# Organization/Thread

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface Thread
```

`Thread` stores multiple [`Post`](../../content/class/Post.md) and notes if they are replies to each other, so we can display these threads later on.

Threads are created for any Post which DetailView is called, if not done already. The calling Post (called `focus` in creation methods) is center-point for determine which Posts are loaded immediately. Posts that are loaded immediately are all steps above `focus` and 2 steps below it, additionally all posts that form a thread by one author with `focus`. Posts not immediately loaded are loaded should they be required by the user.

> Twitter's v2 API does allow for querying the thread, making it easy and economical to contruct. However, Twitter's v1 API as well as Mastodon's API only provide a "replies to" field, which means we need to manually assemble the thread using this field.

| API                | Twitter 1                   | Twitter 2                      | Mastodon         |
| ------------------ | --------------------------- | ------------------------------ | ---------------- |
| Thread field       |                             | `conversation_id`              |                  |
| "Replied to" field | `in_reply_to_status_id_str` | `referenced_tweets.replied_to` | `in_reply_to_id` |

## Static Methods

### `get_replies` {#static_method_get_replies}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public static Post[] get_replies (Post post)
```

Retrieves all replies to the given Post.

### `get_thread` {#static_method_get_thread}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public static Post[] get_thread (Post post)
```

Retrieves all posts that forms a thread from the given start point. When the tree branches, prefer tweets where previous mentioned people reply and those which are going deeper.

## Creation Methods

### `Thread.from_post` {#creation_method_from_post}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Thread.from_post (Post post, string? conversation_id = null)
```

Takes a [`Post`](../../content/class/Post.md) and creates the Thread from it.

## Fields

### `conversation_id` {#field_conversation_id}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square)\

```c#
private string? conversation_id
```

If available, we store the conversation_id so we can fetch additional posts from there.

### `thread_node` {#field_thread_node}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
private GLib.Node<Post> thread_node
```

The node with the [`Post`](../content/class/Post.md) which started this Thread. Used internally to retrieve additional posts.
