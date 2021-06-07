**Project NewCaw** \
Author: Frederick Schenk

# Content/Post

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface Post
```

`Post` is the generic class storing a the content of an status posted on the supported platforms.

| API    | Twitter 1 | Twitter 2 | Mastodon |
| ------ | --------- | --------- | -------- |
| Object | [Tweet](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/tweet) | [Tweet](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/tweet) | [Status](https://docs.joinmastodon.org/entities/status/) |

## Properties

### `id` {#property_id}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string id { get; }
```

The unique identifier a Post has on the platform.

| API   | Twitter 1 | Twitter 2 | Mastodon |
| ----- | --------- | --------- | -------- |
| Field | `id_str`  | `id`      | `id`     |
| Type  | string    | string    | string   |

### `type` {#property_type}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public PostType type { get; }
```

Defines what type this Post is. See [`PostType`](../enum/PostType.md).

### `text` {#property_text}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string text { get; }
```

The text of the Post formatted as am markup-text for the usage in the UI.

> This is the final version formatted for the use in the UI, formatted by [`format_text`](../../utils/namespace/ParseUtils.md#method_format_text), while the original text is found in [`raw_text`](#field_raw_text).

### `author` {#property_author}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public User author { get; }
```

The [`User`](User.md) which posted this post.

| API   | Twitter 1 | Twitter 2   | Mastodon  |
| ----- | --------- | ----------- | --------- |
| Field | `user`    | `author_id` | `account` |
| Type  | object    | id string   | object    |

### `date` {#property_date}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public GLib.DateTime date { get; }
```

The date this Post was posted on the platform.

| API   | Twitter 1    | Twitter 2       | Mastodon        |
| ----- | ------------ | --------------- | --------------- |
| Field | `created_at` | `created_at`    | `created_at`    |
| Type  | string       | ISO 8601 string | ISO 8601 string |

### `url` {#property_url}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string url { get; }
```

A url to open the Post on the website of the used provider.

> Twitter urls have to be generated internally, as there is no field for it.
>
> So, not really neccessary for Twitter (as it is only `twitter.com`, which can be generated on the fly), but as Mastodon has multiple servers, we need to specify it for it, should it be implemented.

| API   | Mastodon        |
| ----- | --------------- |
| Field | `uri` or `url`  |
| Type  | string          |

### `language` {#property_language}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

The language this post was written in, used for offering an translation.

| API   | Twitter 1     | Twitter 2       | Mastodon       |
| ----- | ------------- | --------------- | -------------- |
| Field | `lang`        | `lang`          | `language`     |
| Type  | BCP-47 string | BCP-47 string   | ISO 639 string |

### `referenced_post` {#property_referenced_tweet}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Post? referenced_post { get; }
```

If an post is an repost or quote, this stores the post reposted or quoted.

| API   | Twitter 1                             | Twitter 2           | Mastodon |
| ----- | ------------------------------------- | ------------------- | -------- |
| Field | `retweeted_status` or `quoted_status` | `referenced_tweets` | `reblog` |
| Type  | object                                | array of objects    | object   |

### `thread` {#property_thread}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Thread? thread { get; }
```

The Thread this Post is part of. See [`Thread`](../../organization/class/Thread.md).

### `liked_count` {#property_liked_count}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public int liked_count { get; set; }
```

How often a tweet was liked.

| API   | Twitter 1        | Twitter 2                   | Mastodon          |
| ----- | ---------------- | --------------------------- | ----------------- |
| Field | `favorite_count` | `public_metrics/like_count` | `favorites_count` |
| Type  | int              | int                         | int               |

### `replied_count` {#property_replied_count}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public int replied_count { get; set; }
```

How often a tweet was replied to.

| API   | Twitter 1     | Twitter 2                    | Mastodon        |
| ----- | ------------- | ---------------------------- | --------------- |
| Field | `reply_count` | `public_metrics/reply_count` | `replies_count` |
| Type  | int           | int                          | int             |

### `reposted_count` {#property_reposted_count}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public int reposted_count { get; set; }
```

How often a tweet was reposted or quoted.

| API   | Twitter 1       | Twitter 2                                                     | Mastodon        |
| ----- | --------------- | ------------------------------------------------------------- | --------------- |
| Field | `retweet_count` | `public_metrics/retweet_count` + `public_metrics/quote_count` | `reblogs_count` |
| Type  | int             | int                                                           | int             |

### `source_application` {#property_source_application}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string source_application { get; }
```

Contains the name of which application created this Post.

| API   | Twitter 1 | Twitter 2 | Mastodon      |
| ----- | --------- | --------- | ------------- |
| Field | `source`  | `source`  | `application` |
| Type  | string    | string    | object        |

### `poll` {#property_poll}

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Poll poll { get; }
```

Contains a [`Poll`](Poll.md) object.

| API   | Twitter 2        | Mastodon      |
| ----- | ---------------- | ------------- |
| Field | `includes/polls` | `poll`        |
| Type  | object           | object        |

### `media` {#property_media}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Media[] media { get; }
```

Contains [`Media`](Media.md) attached to this post.

| API   | Twitter 1        | Twitter 2        | Mastodon            |
| ----- | ---------------- | ---------------- | ------------------- |
| Field | `entities/media` | `includes/media` | `media_attachments` |
| Type  | array            | array            | array               |

## Creation Methods

### `Post.from_json` {#creation_method_from_json}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public Post.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

## Methods

### `has_flag`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public bool has_flag (PostFlag flag)
```

Returns if the Post has a specific flag set.

### `set_flag`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public void set_flag (PostFlag flag)
```

Sets a flag for this Post.

### `unset_flag`

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public void unset_flag (PostFlag flag)
```

Removes a flag from this Post.

## Fields

### `flags` {#field_flags}

```c#
private Gee.HashSet<PostFlag> flags
```

Contains flags set for different states of an Post. See [`PostFlag`](../enum/PostFlag.md).

### `raw_text` {#field_raw_text}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
private string raw_text
```

The [`text`](#property_text) as it is recieved from the API, to be later formatted.

| API   | Twitter 1    | Twitter 2    | Mastodon    |
| ----- | ------------ | ------------ | ----------- |
| Field | `text`       | `text`       | `content`   |
| Type  | UTF-8 string | UTF-8 string | HTML string |

### `text_entities` {#field_text_entities}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
private TextEntity[] text_entities
```

All entities found in the text, to provide additional informations for the text formatting. See [TextEntity](../structure/TextEntity.md).

| API   | Twitter 1    | Twitter 2    |
| ----- | ------------ | ------------ |
| Field | `entities`   | `entities`   |
| Type  | array        | array        |
