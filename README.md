## No YouTube shorts
> Redirect YouTube shorts into normal video

|||
|-:|-
|__Example__|[https://www.youtube.com/shorts/1234567890](https://www.youtube.com/shorts/1234567890)
|__Redirect__|`https://www.youtube.com/shorts/*`
|__To__|`https://www.youtube.com/watch?v=$1`
|__Type__|Wildcard
|__Apply To__|Main window (adress bar) <BR> HistoryState

## Twitter-2-Nitter
> Redirect Twitter URLs to Nitter

|||
|-:|-
|__Example__|[https://twitter.com/a_cool_user/status/1234567890](https://twitter.com/a_cool_user/status/1234567890)
|__Redirect__|`https://twitter.com/*`
|__To__|`https://nitter.net/$1`
|__Type__|Wildcard
|__Notes__|Replace the `nitter.net` target with the domain of the instance you want to use.

## Nitter-2-Twitter CDN
> Redirect Nitter media URLs to the Twitter CDN

|||
|-:|-
|__Example__|[https://nitter.net/pic/orig/media%2F1234567890.jpg](https://nitter.net/pic/orig/media%2F1234567890.jpg)
|__Redirect__|`https://nitter.net/pic/orig/*.*`
|__To__|`https://pbs.twimg.com/$1.png`
|__Type__|Wildcard
|__Process__|URL Decode
|__Notes__|Replace `nitter.net` from the target with the domain of the instance you use.

## No old Reddit
> Redirect Old Reddit links to New Reddit

|||
|-:|-
|__Example__|[https://old.reddit.com/r/subreddit/comments/post_id/post_title/](https://old.reddit.com/r/subreddit/comments/post_id/post_title/)
|__Redirect__|`https://old.reddit.com/*`
|__To__|`https://www.reddit.com/$1`
|__Type__|Wildcard

## High quality Discord media
> Clean media URLs from the Discord CDN

|||
|-:|-
|__Example__|[https://cdn.discordapp.com/type/1234567890.jpg?param1=0&param2=0](https://cdn.discordapp.com/type/1234567890.jpg?param1=0&param2=0)
|__Redirect__|`https://cdn.discordapp.com/*/*.*?param1=0&param2=0`
|__To__|`https://cdn.discordapp.com/$1/$2.$3`
|__Type__|Wildcard
|__Notes__|In theory, you could set the pattern to apply to `Images` so that every image inside Discord is fetched at its highest quality. <BR> I have not been able to confirm this.

## High quality Steam Workshop media
> Clean media URLs from the Steam Workshop CDN

|||
|-:|-
|__Example__|[https://steamuserimages-a.akamaihd.net/ugc/1234567890/1234567890/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true](https://steamuserimages-a.akamaihd.net/ugc/1234567890/1234567890/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true)
|__Redirect__|`https://steamuserimages-a.akamaihd.net/ugc/*/*/*`
|__To__|`https://steamuserimages-a.akamaihd.net/ugc/$1/$2/`
|__Type__|Wildcard
|__Notes__|Apply this to `Images` if you want high quality previews

## Wikipedia-2-Wikiwand
> Redirect Wikipedia articles to Wikiwand

|||
|-:|-
|__Example__|[https://en.wikipedia.org/wiki/the-article-you-want-to-read](https://en.wikipedia.org/wiki/the-article-you-want-to-read)
|__Redirect__|`(\w+)\.wikipedia\.org\/.+\/(.+)`
|__To__|`https://www.wikiwand.com/$1/$2`
|__Type__|RegEx
|__Exclude__|`wikipedia\.org\/.+\?oldformat=true`
|__Notes__|Append `?oldformat=true` to the URL to disable redirection.

## No Wikiwand mobile
> Fix Wikiwand mobile redirects

|||
|-:|-
|__Example__|[https://www.wikiwand.com/en.m/the-article-you-want-to-read](https://www.wikiwand.com/en.m/the-article-you-want-to-read)
|__Redirect__|`wikiwand.com\/(\w+)\.m\/(.+)`
|__To__|`https://www.wikiwand.com/$1/$2`
|__Type__|RegEx

## 403 pximg fix
> Redirect i.pximg.net URLs to the Pixiv post

|||
|-:|-
|__Example__|[https://i.pximg.net/img-original/img/1234/12/12/12/12/12/1234567890_p0.png](https://i.pximg.net/img-original/img/1234/12/12/12/12/12/1234567890_p0.png)
|__Redirect__|`i\.pximg\.net\/.+\/(\w+)_p`
|__To__|`https://www.pixiv.net/en/artworks/$1`
|__Type__|RegEx

## Fandom search
> Search FANDOM wiki shortcut

|||
|-:|-
|__Example__|[https://topic.fandom.com/wiki/Topic_Wiki/?](https://topic.fandom.com/wiki/Topic_Wiki/?)
|__Redirect__|`(\w+)\.fandom\.com\/.+(?:\?s)`
|__To__|`https://$1.fandom.com/wiki/Special:Search`
|__Type__|RegEx

<!--
## Title
> Description

|||
|-:|-
|__Example__|[Example URL](Example URL)
|__Redirect__|`Pattern`
|__To__|`Target`
|__Type__|RegEx
-->
