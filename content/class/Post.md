**Project NewCaw** \
Author: Frederick Schenk

# Content/Post

```c#
public interface Post
```

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | [Tweet](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/tweet) | [Tweet](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/tweet) | [Status](https://docs.joinmastodon.org/entities/status/) |

## Properties

### `id` {#property_id}

```c#
public string id { get; }
```

The unique identifier a Post has on the platform.

| Scope        | `TwitterLegacy`   | `Twitter`      | `Mastodon`     |
| ------------ | ----------------- | -------------- | -------------- |
| Available    | ✓                 | ✓              | ✓              |
| API-Endpoint | `id_str` (string) | `id` (string)  | `id` (string)  |

### `type` {#property_type}

```c#
public PostType type { get; }
```

Defines what type this Post is. See [`PostType`](../enum/PostType.md).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `text` {#property_text}

```c#
public string text { get; }
```

The text of the Post formatted as am markup-text for the usage in the UI.

> This is the final version formatted for the use in the UI, formatted by [`format_text`](../../utils/namespace/ParseUtils.md#method_format_text), while the original text is found in [`raw_text`](#field_raw_text).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `author` {#property_author}

```c#
public User author { get; }
```

The [`User`](User.md) which posted this post.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`         |
| ------------ | --------------- | ------------------------- | ------------------ |
| Available    | ✓               | ✓                         | ✓                  |
| API-Endpoint | `user` (object) | `includes.users` (object) | `account` (object) |

### `date` {#property_date}

```c#
public GLib.DateTime date { get; }
```

The date this Post was posted on the platform.

| Scope        | `TwitterLegacy`       | `Twitter`                      | `Mastodon`                     |
| ------------ | --------------------- | ------------------------------ | ------------------------------ |
| Available    | ✓                     | ✓                              | ✓                              |
| API-Endpoint | `created_at` (string) | `created_at` (ISO 8601 string) | `created_at` (ISO 8601 string) |

### `url` {#property_url}

```c#
public string url { get; }
```

A url to open the Post on the website of the used provider.

> Twitter urls have to be generated internally, as there is no field for it.
>
> So, not really neccessary for Twitter (as it is only `twitter.com`, which can be generated on the fly), but as Mastodon has multiple servers, we need to specify it for it, should it be implemented.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`              |
| ------------ | --------------- | -------------- | ----------------------- |
| Available    | ✓               | ✓              | ✓                       |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | `uri` or `url` (string) |

### `language` {#property_language}

The language this post was written in, used for offering an translation.

| Scope        | `TwitterLegacy`        | `Twitter`              | `Mastodon`                  |
| ------------ | ---------------------- | ---------------------- | --------------------------- |
| Available    | ✓                      | ✓                      | ✓                           |
| API-Endpoint | `lang` (BCP-47 string) | `lang` (BCP-47 string) | `language` (ISO 639 string) |

### `referenced_post` {#property_referenced_tweet}

```c#
public Post? referenced_post { get; }
```

If an post is an repost or quote, this stores the post reposted or quoted.

| Scope        | `TwitterLegacy`                                | `Twitter`                   | `Mastodon`        |
| ------------ | ---------------------------------------------- | --------------------------- | ----------------- |
| Available    | ✓                                              | ✓                           | ✓                 |
| API-Endpoint | `retweeted_status` or `quoted_status` (object) | `referenced_tweets` (array) | `reblog` (object) |

### `thread` {#property_thread}

```c#
public Thread? thread { get; }
```

The Thread this Post is part of. See [`Thread`](../../organization/class/Thread.md).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `liked_count` {#property_liked_count}

```c#
public int liked_count { get; }
```

How often a tweet was liked.

| Scope        | `TwitterLegacy`        | `Twitter`                         | `Mastodon`              |
| ------------ | ---------------------- | --------------------------------- | ----------------------- |
| Available    | ✓                      | ✓                                 | ✓                       |
| API-Endpoint | `favorite_count` (int) | `public_metrics/like_count` (int) | `favorites_count` (int) |

### `replied_count` {#property_replied_count}

```c#
public int replied_count { get; }
```

How often a tweet was replied to.

| API   | Twitter 1     | Twitter 2                    | Mastodon        |
| ----- | ------------- | ---------------------------- | --------------- |
| Field | `reply_count` | `public_metrics/reply_count` | `replies_count` |
| Type  | int           | int                          | int             |

| Scope        | `TwitterLegacy`     | `Twitter`                          | `Mastodon`            |
| ------------ | ------------------- | ---------------------------------- | --------------------- |
| Available    | ✓                   | ✓                                  | ✓                     |
| API-Endpoint | `reply_count` (int) | `public_metrics/reply_count` (int) | `replies_count` (int) |

### `reposted_count` {#property_reposted_count}

```c#
public int reposted_count { get; }
```

How often a tweet was reposted or quoted.

| Scope        | `TwitterLegacy`       | `Twitter`                                                           | `Mastodon`            |
| ------------ | --------------------- | ------------------------------------------------------------------- | --------------------- |
| Available    | ✓                     | ✓                                                                   | ✓                     |
| API-Endpoint | `retweet_count` (int) | `public_metrics/retweet_count` + `public_metrics/quote_count` (int) | `reblogs_count` (int) |

### `source_application` {#property_source_application}

```c#
public string source_application { get; }
```

Contains the name of which application created this Post.

| Scope        | `TwitterLegacy`   | `Twitter`         | `Mastodon`             |
| ------------ | ----------------- | ----------------- | ---------------------- |
| Available    | ✓                 | ✓                 | ✓                      |
| API-Endpoint | `source` (string) | `source` (string) | `application` (object) |

### `poll` {#property_poll}

```c#
public Poll poll { get; }
```

Contains a [`Poll`](Poll.md) object.

| Scope        | `TwitterLegacy` | `Twitter`                 | `Mastodon`      |
| ------------ | --------------- | ------------------------- | --------------- |
| Available    | ✗               | ✓                         | ✓               |
| API-Endpoint |                 | `includes/polls` (object) | `poll` (object) |

### `media` {#property_media}

```c#
public Media[] media { get; }
```

Contains [`Media`](Media.md) attached to this post.

| Scope        | `TwitterLegacy`          | `Twitter`                | `Mastodon`                  |
| ------------ | ------------------------ | ------------------------ | --------------------------- |
| Available    | ✓                        | ✓                        | ✓                           |
| API-Endpoint | `entities/media` (array) | `includes/media` (array) | `media_attachments` (array) |

## Creation Methods

### `Post.from_json` {#creation_method_from_json}

```c#
public Post.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Methods

### `has_flag`

```c#
public bool has_flag (PostFlag flag)
```

Returns if the Post has a specific flag set.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `set_flag`

```c#
public void set_flag (PostFlag flag)
```

Sets a flag for this Post.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `unset_flag`

```c#
public void unset_flag (PostFlag flag)
```

Removes a flag from this Post.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Fields

### `flags` {#field_flags}

```c#
private PostFlag flags
```

Contains flags set for different states of an Post. See [`PostFlag`](../enum/PostFlag.md).

> This fields work with an [Flag enum](https://wiki.gnome.org/Projects/Vala/Manual/Enumerated%20types%20(Enums)#Flag_types).

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `raw_text` {#field_raw_text}

```c#
private string raw_text
```

The [`text`](#property_text) as it is recieved from the API, to be later formatted.

| Scope        | `TwitterLegacy`       | `Twitter`             | `Mastodon`              |
| ------------ | --------------------- | --------------------- | ----------------------- |
| Available    | ✓                     | ✓                     | ✓                       |
| API-Endpoint | `text` (UTF-8 string) | `text` (UTF-8 string) | `content` (HTML string) |

### `text_entities` {#field_text_entities}

```c#
private TextEntity[] text_entities
```

All entities found in the text, to provide additional informations for the text formatting. See [TextEntity](../structure/TextEntity.md).

| Scope        | `TwitterLegacy`    | `Twitter`          | `Mastodon`     |
| ------------ | ------------------ | ------------------ | -------------- |
| Available    | ✓                  | ✓                  | ✓              |
| API-Endpoint | `entities` (array) | `entities` (array) | ![Internal][1] |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
