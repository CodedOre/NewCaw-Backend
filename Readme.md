**Project NewCaw** \
Author: Frederick Schenk

# NewCaw

**Bringing Cawbird to 2.0**

## Idea

The idea behind **NewCaw** is to rewrite [Cawbird](https://www.ibboard.co.uk/cawbird) to achive the following goals:

- Improvement of the UI, following GTK Guidelines.
- Improvement of the Backend, making it better maintainable.
- Addition of support for the new Twitter API v2.

## API-Flags

The API-Flags define in which scope a functionality is used and where it get's it's information from.

![API: Internal](https://img.shields.io/badge/API-Internal-green?style=flat-square) - Internal functions in our backend.

![API: Twitter 1](https://img.shields.io/badge/API-Twitter%201-lightgrey?style=flat-square) - The Legacy API from Twitter ([Link](https://developer.twitter.com/en/docs/twitter-api/v1)).

![API: Twitter 2](https://img.shields.io/badge/API-Twitter%202-blue?style=flat-square) - The new API from Twitter, slowly replacing the API v1 ([Link](https://developer.twitter.com/en/docs/twitter-api)).

![API: Twitter 2 (Not yet)](https://img.shields.io/badge/API-Twitter%202%20(Not%20yet)-darkred?style=flat-square) - Required functionality from the new API of Twitter, which is not (yet) available.

![API: Mastodon](https://img.shields.io/badge/API-Mastodon-purple?style=flat-square) - The API from Mastodon, an alternative Service **maybe** included in NewCaw ([Link](https://docs.joinmastodon.org/client/intro/)).

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
