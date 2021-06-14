**Project NewCaw** \
Author: Frederick Schenk

# NewCaw

**Bringing Cawbird to 2.0**

## Idea

The idea behind **NewCaw** is to rewrite [Cawbird](https://www.ibboard.co.uk/cawbird) to achive the following goals:

- Improvement of the UI, following GTK Guidelines.
- Improvement of the Backend, making it better maintainable.
- Addition of support for the new Twitter API v2.

## APIScope-Table

NewCaw is designed with multiple backends in mind, which will subclass the structure here in the following namespaces: The [old API from Twitter](https://developer.twitter.com/en/docs/twitter-api/v1) as `TwitterLegacy`, the [upcoming new API from Twitter](https://developer.twitter.com/en/docs/twitter-api) as `Twitter`, and (if feasable) the [API from Mastodon](https://docs.joinmastodon.org/client/intro/) as `Mastodon`.

As there are multiple API's delivering required data under different names, and also having different functionalities, the following documents contains a APIScope-Table to note for which scopes a element is available and also (if existent) note the API endpoint targeted from the element.

The table is structured as followed:

| Scope        | One of NewCaws backends                                        |
| ------------ | -------------------------------------------------------------- |
| Available    | If the element is available in the scope.                      |
| API-Endpoint | The endpoint of the api. If nothing, then internally filled.   |

## Files

### Content

*The base of social media: The text, the images and more people share.*

**Classes** \
[`Media`](content/class/Media.md) \
 ├ [`Animated`](content/class/Animated.md) \
 ├ [`Picture`](content/class/Picture.md) \
 └ [`Video`](content/class/Video.md) \
[`Poll`](content/class/Poll.md) \
[`Post`](content/class/Post.md) \
[`User`](content/class/User.md) \
 └ [`Profile`](content/class/Profile.md)

**Structures** \
[`PollOption`](content/structure/PollOption.md) \
[`TextEntity`](content/structure/TextEntity.md) \
[`UserDataField`](content/structure/UserDataField.md)

**Enums** \
[`PollFlag`](content/enum/PollFlag.md) \
[`PostType`](content/enum/PostType.md) \
[`PostFlag`](content/enum/PostFlag.md) \
[`UserFlag`](content/enum/UserFlag.md)

### Organization

*Determines how the Content is shown to the user.*

**Classes** \
[`Account`](organization/class/Account.md) \
[`Collection`](organization/class/Collection.md) \
 ├ [`Home`](organization/class/Home.md) \
 ├ [`List`](organization/class/List.md) \
 ├ [`Mentions`](organization/class/Mentions.md) \
 └ [`Timeline`](organization/class/Timeline.md) \
[`Thread`](organization/class/Thread.md)

### Utils

*Additional Utils for some usecases.*

**Namespaces** \
[`ParseUtils`](utils/namespace/ParseUtils.md)

---

*© 2021, Frederick Schenk*
