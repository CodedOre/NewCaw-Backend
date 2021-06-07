**Project NewCaw** \
Author: Frederick Schenk

# Content/Profile

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface Profile : User
```

`Profile` is an subclass of [`User`](User.md) which provides additional information that `User` does not contain.

> The main usecase for `Profile` would be the profile page. Instead of just using `User` and calling additional data when needed I want to use a backend class in order to achieve two things: First to have a decisive split between back- and frontend (as in frontend only displays and backend only gets data), and secondly to also have an option to cache the data should we want to use it again.

| API    | Twitter 1 | Twitter 2 | Mastodon |
| ------ | --------- | --------- | -------- |
| Object | [User](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/user) | [User](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user) | [Account](https://docs.joinmastodon.org/entities/account/) |

## Properties

### `description` {#property_description}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string description { get; }
```

How the user descripes itself.

> This is the final version formatted for the use in the UI, formatted by [`format_text`](../../utils/namespace/ParseUtils.md#method_format_text), while the original text is found in [`raw_description`](#field_raw_description).

### `created_at` {#property_created_at}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string created_at { get; }
```

When this Profile was created.

| API   | Twitter 1    | Twitter 2       | Mastodon        |
| ----- | ------------ | --------------- | --------------- |
| Field | `created_at` | `created_at`    | `created_at`    |
| Type  | string       | ISO 8601 string | ISO 8601 string |

### `fields` {#property_fields}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public UserDataField[] fields { get; }
```

Fields providing additional informations about the User. See [`UserDataField`](../structure/UserDataField.md).

| API   | Twitter 1          | Twitter 2          | Mastodon |
| ----- | ------------------ | ------------------ | -------- |
| Field | `location` & `url` | `location` & `url` | `fields` |
| Type  | string             | string             | array    |

### `header` {#property_header}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Picture header { get; }
```

The header image of the User (for the profile page), stored as a [`Picture`](Picture.md).

> Mastodon provides the option to use a animated GIF (which we store as a [`Animated`](Animated.md)) as a header. For now, we will not consider this option as it makes the code more complex and use always the static variant.

| API   | Twitter 1            | Twitter 2 | Mastodon        |
| ----- | -------------------- | --------- | --------------- |
| Field | `profile_banner_url` |           | `header_static` |
| Type  | url string           |           | url string      |

### `followers_count` {#property_followers_count}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public uint followers_count { get; set; }
```

How many people are following this User.

| API   | Twitter 1         | Twitter 2                        | Mastodon          |
| ----- | ----------------- | -------------------------------- | ------------------|
| Field | `followers_count` | `public_metrics/followers_count` | `followers_count` |
| Type  | int               | int                              | int               |

### `following_count` {#property_following_count}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public uint following_count { get; set; }
```

How many people this User follows.

| API   | Twitter 1       | Twitter 2                        | Mastodon          |
| ----- | --------------- | -------------------------------- | ------------------|
| Field | `friends_count` | `public_metrics/following_count` | `following_count` |
| Type  | int             | int                              | int               |

### `posts_count` {#property_post_count}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public uint posts_count { get; set; }
```

How many posts this User wrote.

| API   | Twitter 1        | Twitter 2                    | Mastodon         |
| ----- | ---------------- | ---------------------------- | -----------------|
| Field | `statuses_count` | `public_metrics/tweet_count` | `statuses_count` |
| Type  | int              | int                          | int              |

> ### Inherited from [`User`](../../content/class/User.md)
> 
> [**`id`**](../../content/class/User.md#property_id)
> 
> [**`display_name`**](../../content/class/User.md#property_display_name)
> 
> [**`username`**](../../content/class/User.md#property_username)
> 
> [**`avatar`**](../../content/class/User.md#property_avatar)

## Creation Methods

### `from_json` {#creation_method_from_json}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Profile.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

### `from_user` {#creation_method_from_user}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Profile.from_user (User user)
```

"Converts" an existing `User` to a `Profile` and loads the additional information needed.

## Methods

> ### Inherited from [`User`](../../content/class/User.md)
> 
> [**`has_flags`**](../../content/class/User.md#method_has_flags)
> 
> [**`set_flags`**](../../content/class/User.md#method_set_flags)
> 
> [**`unset_flags`**](../../content/class/User.md#method_unset_flags)

## Fields

### `raw_description` {#field_raw_description}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
private string raw_description
```

The [`description`](#property_description) as it is recieved from the API, to be later formatted.

| API   | Twitter 1     | Twitter 2     | Mastodon |
| ----- | ------------- | ------------- | -------- |
| Field | `description` | `description` | `note`   |
| Type  | string        | string        | string   |

### `description_entities` {#field_description_entities}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
private TextEntity[] description_entities
```

All entities found in the text, to provide additional informations for the text formatting. See [TextEntity](../structure/TextEntity.md).

| API   | Twitter 1    | Twitter 2    |
| ----- | ------------ | ------------ |
| Field | `entities`   | `entities`   |
| Type  | array        | array        |

> ### Inherited from [`User`](../../content/class/User.md)
> 
> [**`flags`**](../../content/class/User.md#field_flags)
