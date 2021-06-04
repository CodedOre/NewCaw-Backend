**Project NewCaw** \
Author: Frederick Schenk

# Organization/List

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface List : Collection
```

`List` stores a list containing multiple posts and is a subclass of [`Collection`](Collection.md).

| API      | Twitter 1 | Twitter 2 | Mastodon |
| -------- | --------- | --------- | -------- |
| Function | [`lists/show`](https://developer.twitter.com/en/docs/twitter-api/v1/accounts-and-users/create-manage-lists/api-reference/get-lists-show) |  | [`timelines/list`](https://docs.joinmastodon.org/methods/timelines/) |

## Properties

### `id` {#property_id}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string id { get; }
```

The unique identifier for this list.

| API   | Twitter 1 | Twitter 2 | Mastodon |
| ----- | --------- | --------- | -------- |
| Field | `list_id` |           | `id`     |
| Type  | string    |           | string   |

### `title`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string title { get; }
```

The title of the list.

| API   | Twitter 1 | Twitter 2 | Mastodon |
| ----- | --------- | --------- | -------- |
| Field | `name`    |           | `title`  |
| Type  | string    |           | string   |

### `title`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string title { get; }
```

The title of the list.

| API   | Twitter 1 | Twitter 2 | Mastodon |
| ----- | --------- | --------- | -------- |
| Field | `name`    |           | `title`  |
| Type  | string    |           | string   |

### `description` {#property_description}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square)

```c#
public string description { get; }
```

A description of the list.

| API   | Twitter 1     | Twitter 2 |
| ----- | ------------- | --------- |
| Field | `description` |           |
| Type  | string        |           |

### `public_visible` {#property_public_visible}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square)

```c#
public bool public_visible { get; }
```

If the list is visible to the public.

| API   | Twitter 1 | Twitter 2 |
| ----- | --------- | --------- |
| Field | `mode`    |           |
| Type  | enum      |           |

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`last_viewed_post`**](Collection.md#property_last_viewed_post)

## Creation Methods

### `List`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public List (string id)
```

Get a specified list (by it's id) and pulls the posts.

## Methods

### `get_posts` {#method_get_posts}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Post[] get_posts ()
```

Returns [`post_list`](#field_post_list) to the caller.

### `get_new_posts` {#method_get_new_posts}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Post[] get_new_posts ()
```

Calls the API to load new posts and returns them.

## Fields

### `list_members` {#field_list_members}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public User[] list_members
```

All list containing [`User`](../../content/class/User.md) that are part of this list.

| API      | Twitter 1       | Twitter 2 | Mastodon         |
| -------- | --------------- | --------- | ---------------- |
| Function | `lists/members` |           | `lists/accounts` |

> ### Inherited from [`User`](../../content/class/User.md)
> 
> [**`flags`**](../../content/class/User.md#field_flags)

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`post_list`**](Collection.md#field_post_list)
> 
> [**`last_pulled_post`**](Collection.md#field_last_pulled_post)
