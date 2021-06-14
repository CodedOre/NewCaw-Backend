**Project NewCaw** \
Author: Frederick Schenk

# Content/Media

```c#
public interface Media
```

`Media` represents a generic interface for media contained in a [`Post`](Post.md). It is subclassed by classes which implements actual media types such as images or video.

| Scope        | `TwitterLegacy` | `Twitter` | `Mastodon` |
| ------------ | --------------- | --------- | ---------- |
| Available    | ✓               | ✓         | ✓          |
| API-Endpoint | [Media](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/entities#media) | [Media](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/media) | [Attachment](https://docs.joinmastodon.org/entities/attachment/) |

## Properties

### `id` {#property_id}

```c#
public string id { get; }
```

The unique identifier for this media object.

| Scope        | `TwitterLegacy`   | `Twitter`            | `Mastodon`    |
| ------------ | ----------------- | -------------------- | ------------- |
| Available    | ✓                 | ✓                    | ✓             |
| API-Endpoint | `id_str` (string) | `media_key` (string) | `id` (string) |

### `media_url` {#property_media_url}

```c#
public string media_url { get; }
```

The url to the full-scale media.

| Scope        | `TwitterLegacy`            | `Twitter`                 | `Mastodon`     |
| ------------ | -------------------------- | ------------------------- | -------------- |
| Available    | ✓                          | ✓                         | ✓              |
| API-Endpoint | `media_url_https` (string) | ![No API endpoint yet][2] | `url` (string) |

### `preview_url` {#property_preview_url}

```c#-*
public string preview_url { get; }
```

The url to an preview image for the timeline.

| Scope        | `TwitterLegacy`            | `Twitter`                    | `Mastodon`             |
| ------------ | -------------------------- | ---------------------------- | ---------------------- |
| Available    | ✓                          | ✓                            | ✓                      |
| API-Endpoint | `media_url_https` (string) | `preview_image_url` (string) | `preview_url` (string) |

### `preview_image` {#property_preview_image}

```c#
public Gdk.Pixbuf preview_image { get; }
```

The preview image to display in the timeline.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `media_blurhash` {#property_media_blurhash}

```c#
public string preview_blurhash { get; }
```

A hash computed by the BlurHash algorithm, for generating colorful preview thumbnails when media has not been downloaded yet (or when sensitive media is blurred).

| Scope        | `TwitterLegacy` | `Twitter` | `Mastodon`          |
| ------------ | --------------- | --------- | ------------------- |
| Available    | ✗               | ✗         | ✓                   |
| API-Endpoint |                 |           | `blurhash` (string) |

### `alt_text` {#property_alt_text}

```c#
public string alt_text { get; }
```

A description of the media for display on hover.

| Scope        | `TwitterLegacy`                 | `Twitter`                 | `Mastodon`             |
| ------------ | ------------------------------- | ------------------------- | ---------------------- |
| Available    | ✓                               | ✓                         | ✓                      |
| API-Endpoint | `include_ext_alt_text` (string) | ![No API endpoint yet][2] | `description` (string) |

### `height` {#property_height}

```c#
public int height { get; }
```

The height of the media.

| Scope        | `TwitterLegacy`       | `Twitter`      | `Mastodon`                   |
| ------------ | --------------------- | -------------- | ---------------------------- |
| Available    | ✓                     | ✓              | ✓                            |
| API-Endpoint | `sizes/large/h` (int) | `height` (int) | `meta/original/height` (int) |

### `width` {#property_width}

```c#
public int width { get; }
```

The width of the media.

| Scope        | `TwitterLegacy`       | `Twitter`     | `Mastodon`                  |
| ------------ | --------------------- | ------------- | --------------------------- |
| Available    | ✓                     | ✓             | ✓                           |
| API-Endpoint | `sizes/large/w` (int) | `width` (int) | `meta/original/width` (int) |

### `load_preview_progress` {#property_load_preview_progress}

```c#
public double progress_load_preview { get; }
```

How far the loading of the preview image is completed.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `load_media_progress` {#property_load_media_progress}

```c#
public double progress_load_preview { get; }
```

How far the loading of the media is completed.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Methods

### `load_preview` {#method_load_preview}

```c#
public async void load_preview ()
```

Loads the preview image. Activates [`load_preview_completed`](#signal_load_preview_completed) on completion.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `load_media` {#method_load_media}

```c#
public abstract async void load_media ()
```

Loads the media and returns it. Activates [`load_media_completed`](#signal_load_media_completed) on completion.

> Neither `Media` nor it's subclass stores the full media. Instead the function loads it and hands it over to the Media Viewer, which clears the media from memory after it is closed.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Signals

### `load_preview_completed` {#signal_load_preview_completed}

```c#
public signal void load_preview_completed ()
```

Activated when [`load_preview`](#method_load_preview) is completed.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

### `load_media_completed` {#signal_load_media_completed}

```c#
public signal void load_media_completed ()
```

Activated when [`load_media`](#method_load_media) is completed.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
