**Project NewCaw** \
Author: Frederick Schenk

# Organization/Mentions

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface Mentions : Collection
```

`Mentions` subclasses [`Collection`](Collection.md) and contains recent posts that mentions a user.

| API      | Twitter 1 | Twitter 2 | Mastodon |
| -------- | --------- | --------- | -------- |
| Function | [`statuses/mentions_timeline`](https://developer.twitter.com/en/docs/twitter-api/v1/tweets/timelines/api-reference/get-statuses-mentions_timeline) | [`users/mentions`](https://developer.twitter.com/en/docs/twitter-api/tweets/timelines/api-reference/get-users-id-mentions) | [`notifications` *(with any but mentions excluded)*](https://docs.joinmastodon.org/methods/notifications/) |

## Properties

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`last_viewed_post`**](Collection.md#property_last_viewed_post)

## Creation Methods

### `Mentions`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Mentions (Account account)
```

Creates `Mentions` for a given [`Account`](Account.md) and pulls posts.

## Methods

### `get_posts` {#method_get_posts}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Post[] get_posts ()
```

Returns [`post_list`](#field_post_list) to the caller.

### `get_new_posts` {#method_get_new_posts}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Post[] get_new_posts ()
```

Calls the API to load new posts and returns them.

## Fields

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`post_list`**](Collection.md#field_post_list)
> 
> [**`last_pulled_post`**](Collection.md#field_last_pulled_post)
