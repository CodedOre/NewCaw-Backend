**Project NewCaw** \
Author: Frederick Schenk

# Organization/Account

```c#
public interface Account : Profile
```

`Account` is a subclass of [`Profile`](../../content/class/Profile.md) which manages a account which uses Cawbird.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

## Properties

### `access_proxy`

```c#
public Rest.OAuthProxy access_proxy { get; }
```

The proxy that allows to do an API-call.

| Scope        | `TwitterLegacy` | `Twitter`      | `Mastodon`     |
| ------------ | --------------- | -------------- | -------------- |
| Available    | ✓               | ✓              | ✓              |
| API-Endpoint | ![Internal][1]  | ![Internal][1] | ![Internal][1] |

> ### Inherited from [`Profile`](../../content/class/Profile.md)
> 
> [**`description`**](../../content/class/Profile.md#property_description)
> 
> [**`created_at`**](../../content/class/Profile.md#property_created_at)
> 
> [**`fields`**](../../content/class/Profile.md#property_fields)
> 
> [**`header`**](../../content/class/Profile.md#property_header)
> 
> [**`followers_count`**](../../content/class/Profile.md#property_followers_count)
> 
> [**`following_count`**](../../content/class/Profile.md#property_following_count)
> 
> [**`posts_count`**](../../content/class/Profile.md#property_posts_count)
> 
> > #### Inherited from [`User`](../../content/class/User.md)
> > 
> > [**`id`**](../../content/class/User.md#property_id)
> > 
> > [**`display_name`**](../../content/class/User.md#property_display_name)
> > 
> > [**`username`**](../../content/class/User.md#property_username)
> > 
> > [**`avatar`**](../../content/class/User.md#property_avatar)

## Creation Methods

> Not included yet...

## Methods

> ### Inherited from [`Profile`](../../content/class/Profile.md)
> 
> > #### Inherited from [`User`](../../content/class/User.md)
> > 
> > [**`has_flags`**](../../content/class/User.md#method_has_flags)
> > 
> > [**`set_flags`**](../../content/class/User.md#method_set_flags)
> > 
> > [**`unset_flags`**](../../content/class/User.md#method_unset_flags)

## Fields

> ### Inherited from [`Profile`](../../content/class/Profile.md)
> 
> [**`raw_description`**](../../content/class/Profile.md#field_raw_description)
> 
> [**`description_entities`**](../../content/class/Profile.md#field_description_entities)
> 
> > #### Inherited from [`User`](../../content/class/User.md)
> > 
> > [**`flags`**](../../content/class/User.md#field_flags)

---

*© 2021, Frederick Schenk*

[1]: https://img.shields.io/badge/-Internal-yellow?style=flat-square
[2]: https://img.shields.io/badge/-No%20API%20endpoint%20yet-red?style=flat-square
