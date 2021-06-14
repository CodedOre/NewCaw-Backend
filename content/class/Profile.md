**Project NewCaw** \
Author: Frederick Schenk

# Content/Profile

```c#
public interface Profile : User
```

`Profile` is an subclass of [`User`](User.md) which provides additional information that `User` does not contain.

> The main usecase for `Profile` would be the profile page. Instead of just using `User` and calling additional data when needed I want to use a backend class in order to achieve two things: First to have a decisive split between back- and frontend (as in frontend only displays and backend only gets data), and secondly to also have an option to cache the data should we want to use it again.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [User](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/user) | [User](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/user) | [Account](https://docs.joinmastodon.org/entities/account/) |

## Properties

### `description` {#property_description}

```c#
public string description { get; }
```

How the user descripes itself.

> This is the final version formatted for the use in the UI, formatted by [`format_text`](../../utils/namespace/ParseUtils.md#method_format_text), while the original text is found in [`raw_description`](#field_raw_description).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `created_at` {#property_created_at}

```c#
public string created_at { get; }
```

When this Profile was created.

| Scope        | `TwitterLegacy`       | `Twitter`                      | `Mastodon`                     |
| ------------ | --------------------- | ------------------------------ | ------------------------------ |
| Available    | ✓                     | ✓                              | ✓                              |
| API-Endpoint | `created_at` (string) | `created_at` (ISO 8601 string) | `created_at` (ISO 8601 string) |

### `fields` {#property_fields}

```c#
public UserDataField[] fields { get; }
```

Fields providing additional informations about the User. See [`UserDataField`](../structure/UserDataField.md).

| Scope        | `TwitterLegacy`             | `Twitter`                   | `Mastodon`       |
| ------------ | --------------------------- | --------------------------- | ---------------- |
| Available    | ✓                           | ✓                           | ✓                |
| API-Endpoint | `location` & `url` (string) | `location` & `url` (string) | `fields` (array) |

### `header` {#property_header}

```c#
public Picture header { get; }
```

The header image of the User (for the profile page), stored as a [`Picture`](Picture.md).

> Mastodon provides the option to use a animated GIF (which we store as a [`Animated`](Animated.md)) as a header. For now, we will not consider this option as it makes the code more complex and use always the static variant.

| Scope        | `TwitterLegacy`               | `Twitter`                 | `Mastodon`               |
| ------------ | ----------------------------- | ------------------------- | ------------------------ |
| Available    | ✓                             | ✓                         | ✓                        |
| API-Endpoint | `profile_banner_url` (string) | ![No API endpoint yet][2] | `header_static` (string) |

### `followers_count` {#property_followers_count}

```c#
public uint followers_count { get; set; }
```

How many people are following this User.

| Scope        | `TwitterLegacy`         | `Twitter`                              | `Mastodon`              |
| ------------ | ----------------------- | -------------------------------------- | ----------------------- |
| Available    | ✓                       | ✓                                      | ✓                       |
| API-Endpoint | `followers_count` (int) | `public_metrics/followers_count` (int) | `followers_count` (int) |

### `following_count` {#property_following_count}

```c#
public uint following_count { get; set; }
```

How many people this User follows.

| Scope        | `TwitterLegacy`       | `Twitter`                              | `Mastodon`              |
| ------------ | --------------------- | -------------------------------------- | ----------------------- |
| Available    | ✓                     | ✓                                      | ✓                       |
| API-Endpoint | `friends_count` (int) | `public_metrics/following_count` (int) | `following_count` (int) |

### `posts_count` {#property_post_count}

```c#
public uint posts_count { get; set; }
```

How many posts this User wrote.

| Scope        | `TwitterLegacy`        | `Twitter`                          | `Mastodon`             |
| ------------ | ---------------------- | ---------------------------------- | ---------------------- |
| Available    | ✓                      | ✓                                  | ✓                      |
| API-Endpoint | `statuses_count` (int) | `public_metrics/tweet_count` (int) | `statuses_count` (int) |

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

```c#
public Profile.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `from_user` {#creation_method_from_user}

```c#
public Profile.from_user (User user)
```

"Converts" an existing `User` to a `Profile` and loads the additional information needed.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

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

```c#
private string raw_description
```

The [`description`](#property_description) as it is recieved from the API, to be later formatted.

| Scope        | `TwitterLegacy`        | `Twitter`              | `Mastodon`      |
| ------------ | ---------------------- | ---------------------- | --------------- |
| Available    | ✓                      | ✓                      | ✓               |
| API-Endpoint | `description` (string) | `description` (string) | `note` (string) |

### `description_entities` {#field_description_entities}

```c#
private TextEntity[] description_entities
```

All entities found in the text, to provide additional informations for the text formatting. See [TextEntity](../structure/TextEntity.md).

| Scope        | `TwitterLegacy`     | `Twitter`           | `Mastodon`     |
| ------------ | ------------------- | ------------------- | -------------- |
| Available    | ✓                   | ✓                   | ✓              |
| API-Endpoint | `entities` (entity) | `entities` (entity) | ![Internal][1] |

> ### Inherited from [`User`](../../content/class/User.md)
> 
> [**`flags`**](../../content/class/User.md#field_flags)

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
