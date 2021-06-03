**Project NewCaw** \
Author: Frederick Schenk

# Content/Media

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public interface Media
```

`Media` represents a generic interface for media contained in a [`Post`](Post.md). It is subclassed by classes which implements actual media types such as images or video.

| API    | Twitter 1 | Twitter 2 | Mastodon |
| ------ | --------- | --------- | -------- |
| Object | [Media](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/entities#media) | [Media](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/media) | [Attachment](https://docs.joinmastodon.org/entities/attachment/) |

## Properties

### `id` {#property_id}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string id { get; }
```

The unique identifier for this media object.

| API   | Twitter 1 | Twitter 2   | Mastodon |
| ----- | --------- | ----------- | -------- |
| Field | `id_str`  | `media_key` | `id`     |
| Type  | string    | string      | string   |

### `media_url` {#property_media_url}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string media_url { get; }
```

The url to the full-scale media.

| API   | Twitter 1         | Twitter 2 | Mastodon |
| ----- | ----------------- | --------- | -------- |
| Field | `media_url_https` |           | `url`    |
| Type  | string            |           | string   |

### `preview_url` {#property_preview_url}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string preview_url { get; }
```

The url to an preview image for the timeline.

| API   | Twitter 1         | Twitter 2           | Mastodon      |
| ----- | ----------------- | ------------------- | ------------- |
| Field | `media_url_https` | `preview_image_url` | `preview_url` |
| Type  | string            | string              | string        |

### `preview_image` {#property_preview_image}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public Gdk.Pixbuf preview_image { get; }
```

The preview image to display in the timeline.

> When the image was loaded it returns [`preview_image_data`](#field_preview_image_data), otherwise it returns `null` and initiates [`load_preview`](#method_load_preview).

### `media_blurhash` {#property_media_blurhash}

![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string preview_blurhash { get; }
```

A hash computed by the BlurHash algorithm, for generating colorful preview thumbnails when media has not been downloaded yet (or when sensitive media is blurred).

| API   | Mastodon   |
| ----- | ---------- |
| Field | `blurhash` |
| Type  | string     |

### `alt_text` {#property_alt_text}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public string alt_text { get; }
```

A description of the media for display on hover.

| API   | Twitter 1              | Twitter 2 | Mastodon |
| ----- | ---------------------- | --------- | -------- |
| Field | `include_ext_alt_text` |           | `url`    |
| Type  | string                 |           | string   |

### `height` {#property_height}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public int height { get; }
```

The height of the media.

| API   | Twitter 1       | Twitter 2 | Mastodon               |
| ----- | --------------- | --------- | ---------------------- |
| Field | `sizes/large/h` | `height`  | `meta/original/height` |
| Type  | int             | int       | int                    |

### `width` {#property_width}

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) ![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) ![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square)

```c#
public int width { get; }
```

The width of the media.

| API   | Twitter 1       | Twitter 2 | Mastodon              |
| ----- | --------------- | --------- | --------------------- |
| Field | `sizes/large/w` | `width`   | `meta/original/width` |
| Type  | int             | int       | int                   |

### `load_preview_progress` {#property_load_preview_progress}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public double progress_load_preview { get; }
```

How far the loading of the preview image is completed.

### `load_media_progress` {#property_load_media_progress}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public double progress_load_preview { get; }
```

How far the loading of the media is completed.

## Methods

### `load_preview` {#method_load_preview}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public async void load_preview ()
```

Loads the preview image. Activates [`load_preview_completed`](#signal_load_preview_completed) on completion.

### `load_media` {#method_load_media}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public abstract async void load_media ()
```

Loads the media and returns it. Activates [`load_media_completed`](#signal_load_media_completed) on completion.

> Neither `Media` nor it's subclass stores the full media. Instead the function loads it and hands it over to the Media Viewer, which clears the media from memory after it is closed.

## Signals

### `load_preview_completed` {#signal_load_preview_completed}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public signal void load_preview_completed ()
```

Activated when [`load_preview`](#method_load_preview) is completed.

### `load_media_completed` {#signal_load_media_completed}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public signal void load_media_completed ()
```

Activated when [`load_media`](#method_load_media) is completed.

## Fields

### `preview_image_data` {#field_preview_image_data}

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square)\

```c#
public Cairo.ImageSurface preview_image_data
```

The stored preview image to display in the timeline.
