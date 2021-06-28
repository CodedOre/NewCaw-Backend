**Project NewCaw** \
Author: Frederick Schenk

# Organization/Timeline

```c#
public interface Timeline : Collection
```

`Timeline` inheriteds [`Collection`](Collection.md) and provides support for user timelines.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [`statuses/user_timeline`](https://developer.twitter.com/en/docs/twitter-api/v1/tweets/timelines/api-reference/get-statuses-user_timeline) | [`users/tweets`](https://developer.twitter.com/en/docs/twitter-api/tweets/timelines/api-reference/get-users-id-tweets) | [`accounts/statuses`](https://docs.joinmastodon.org/methods/accounts/) |

## Properties

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`last_viewed_post`**](Collection.md#property_last_viewed_post)

## Creation Methods

### `Timeline`

```c#
public Timeline (User user)
```

Creates a timeline for a given [`User`](../../content/class/User.md) and pulls posts.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Methods

### `get_new_posts` {#method_get_new_posts}

```c#
public abstract Post[] get_new_posts ()
```

Calls the API to load new posts and returns them.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`get_posts`**](Collection.md#method_get_posts)

## Fields

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`post_list`**](Collection.md#field_post_list)
> 
> [**`last_pulled_post`**](Collection.md#field_last_pulled_post)

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
