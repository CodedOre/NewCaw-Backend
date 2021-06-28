**Project NewCaw** \
Author: Frederick Schenk

# Content/Video

```c#
public interface Video : Media
```

`Video` is a subclass of [`Media`](Media.md) which manages a video from a platform.

| Scope        | `TwitterLegacy` | `Twitter` | `Mastodon` |
| ------------ | --------------- | --------- | ---------- |
| Available    | ✓               | ✓         | ✓          |
| API-Endpoint | [Media](https://developer.twitter.com/en/docs/twitter-api/v1/data-dictionary/object-model/entities#media) | [Media](https://developer.twitter.com/en/docs/twitter-api/data-dictionary/object-model/media) | [Attachment](https://docs.joinmastodon.org/entities/attachment/) |

## Properties

> ### Inherited from [`Media`](Media.md)
> 
> [**`id`**](Media.md#property_id)
> 
> [**`media_url`**](Media.md#property_media_url)
> 
> [**`preview_url`**](Media.md#property_preview_url)
> 
> [**`preview_image`**](Media.md#property_preview_image)
> 
> [**`media_blurhash`**](Media.md#property_media_blurhash)
> 
> [**`alt_text`**](Media.md#property_alt_text)
> 
> [**`height`**](Media.md#property_height)
> 
> [**`width`**](Media.md#property_width)
> 
> [**`load_preview_progress`**](Media.md#property_load_preview_progress)
> 
> [**`load_media_progress`**](Media.md#property_load_media_progress)

## Creation Methods

### `Picture.from_json` {#creation_method_from_json}

```c#
public Picture.from_json (Json.Object obj)
```

Creates a new object out of a given Json object from other points.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Methods

### `load_media` {#method_load_media}

```c#
public async Gtk.MediaFile load_media ()
```

Loads the media and returns it. Activates [`load_media_completed`](Media.md#signal_load_media_completed) on completion.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

> ### Inherited from [`Media`](Media.md)
> 
> [**`load_preview`**](Media.md#method_load_preview)

## Signals

> ### Inherited from [`Media`](Media.md)
> 
> [**`load_preview_completed`**](Media.md#signal_load_preview_completed)
> 
> [**`load_media_completed`**](Media.md#signal_load_media_completed)

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
