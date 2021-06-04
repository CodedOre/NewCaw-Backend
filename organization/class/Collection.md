**Project NewCaw** \
Author: Frederick Schenk

# Organization/Collection

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public interface Collection
```

`Collection` is a interface which provides basic elements which are shared by [`Timeline`](Timeline.md), [`Mentions`](Mentions.md) and [`List`](List.md).

## Properties

### `last_viewed_post` {#property_last_viewed_post}

```c#
public string last_viewed_post { get; set; }
```

The id of the lastest post that was viewed by the user. Setable by the frontend.

## Methods

### `get_posts` {#method_get_posts}

```c#
public abstract Post[] get_posts ()
```

Returns [`post_list`](#field_post_list) to the caller.

### `get_new_posts` {#method_get_new_posts}

```c#
public abstract Post[] get_new_posts ()
```

Calls the API to load new posts and returns them.

## Fields

### `post_list` {#field_post_list}

```c#
private Post[] post_list
```

Contains references to all posts in chronological order.

### `last_pulled_post` {#field_last_pulled_post}

```c#
private string last_pulled_post
```

The id of the post that has been loaded. Used to determine to which point [`get_new_posts`](#method_get_new_posts) calls new posts.
