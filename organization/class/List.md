**Project NewCaw** \
Author: Frederick Schenk

# Organization/List

```c#
public interface List : Collection
```

`List` stores a list containing multiple posts and is a subclass of [`Collection`](Collection.md).

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`     |
| ------------ | --------------- | ------------------------- | -------------- |
| Available    | ✓               | ✓                         | ✓              |
| API-Endpoint | [`lists/show`](https://developer.twitter.com/en/docs/twitter-api/v1/accounts-and-users/create-manage-lists/api-reference/get-lists-show) | ![No API endpoint yet][2] | [`timelines/list`](https://docs.joinmastodon.org/methods/timelines/) |

## Properties

### `id` {#property_id}

```c#
public string id { get; }
```

The unique identifier for this list.

| Scope        | `TwitterLegacy`    | `Twitter`                 | `Mastodon`     |
| ------------ | ------------------ | ------------------------- | -------------- |
| Available    | ✓                  | ✓                         | ✓              |
| API-Endpoint | `list_id` (string) | ![No API endpoint yet][2] | `id` (string)  |

### `title`

```c#
public string title { get; }
```

The title of the list.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`       |
| ------------ | --------------- | ------------------------- | ---------------- |
| Available    | ✓               | ✓                         | ✓                |
| API-Endpoint | `name` (string) | ![No API endpoint yet][2] | `title` (string) |

### `title`

```c#
public string title { get; }
```

The title of the list.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`       |
| ------------ | --------------- | ------------------------- | ---------------- |
| Available    | ✓               | ✓                         | ✓                |
| API-Endpoint | `name` (string) | ![No API endpoint yet][2] | `title` (string) |

### `description` {#property_description}

```c#
public string description { get; }
```

A description of the list.

| Scope        | `TwitterLegacy`        | `Twitter`                 | `Mastodon`     |
| ------------ | ---------------------- | ------------------------- | -------------- |
| Available    | ✓                      | ✓                         | ✗              |
| API-Endpoint | `description` (string) | ![No API endpoint yet][2] |                |

### `public_visible` {#property_public_visible}

```c#
public bool public_visible { get; }
```

If the list is visible to the public.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`     |
| ------------ | --------------- | ------------------------- | -------------- |
| Available    | ✓               | ✓                         | ✗              |
| API-Endpoint | `mode` (enum)   | ![No API endpoint yet][2] |                |

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`last_viewed_post`**](Collection.md#property_last_viewed_post)

## Creation Methods

### `List`

```c#
public List (string id)
```

Get a specified list (by it's id) and pulls the posts.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`     |
| ------------ | --------------- | ------------------------- | -------------- |
| Available    | ✓               | ✓                         | ✓              |
| API-Endpoint | ![Internal][1]  | ![No API endpoint yet][2] | ![Internal][1] |

## Methods

### `get_new_posts` {#method_get_new_posts}

```c#
public abstract Post[] get_new_posts ()
```

Calls the API to load new posts and returns them.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`     |
| ------------ | --------------- | ------------------------- | -------------- |
| Available    | ✓               | ✓                         | ✓              |
| API-Endpoint | ![Internal][1]  | ![No API endpoint yet][2] | ![Internal][1] |

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`get_posts`**](Collection.md#method_get_posts)

## Fields

### `list_members` {#field_list_members}

```c#
public User[] list_members
```

All list containing [`User`](../../content/class/User.md) that are part of this list.

| Scope        | `TwitterLegacy`            | `Twitter`                 | `Mastodon`                  |
| ------------ | -------------------------- | ------------------------- | --------------------------- |
| Available    | ✓                          | ✓                         | ✓                           |
| API-Endpoint | `lists/members` (function) | ![No API endpoint yet][2] | `lists/accounts` (function) |

> ### Inherited from [`Collection`](Collection.md)
> 
> [**`post_list`**](Collection.md#field_post_list)
> 
> [**`last_pulled_post`**](Collection.md#field_last_pulled_post)

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
