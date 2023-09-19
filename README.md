## No YouTube shorts
> Redirect YouTube shorts into normal video

|||
|-|-
|__Example__|[https://www.youtube.com/shorts/1234567890](https://www.youtube.com/shorts/1234567890)
|__Pattern__|`https?://www\.youtube\.com/shorts/(.+)`
|__Target__|`https://www.youtube.com/watch?v=$1`
|__Type__|RegEx

## Twitter-2-Nitter
> Redirect Twitter URLs to Nitter

|||
|-|-
|__Example__|[https://twitter.com/a_cool_user/status/1234567890](https://twitter.com/a_cool_user/status/1234567890)
|__Pattern__|`https?://twitter\.com/(.+)`
|__Target__|`https://my.nitter.instance/$1`
|__Type__|RegEx
|__Notes__|Make sure to replace the `my.nitter.instance` part of the target with the domain from the instance you want to use.

## Nitter User Profile Fix
> Fix Nitter URLs when redirected from a user profile

|||
|-|-
|__Example__|[https://my.nitter.instance/i/flow/login?redirect_after_login=%2Fa_cool_user](https://my.nitter.instance/i/flow/login?redirect_after_login=%2Fa_cool_user)
|__Pattern__|`https?://my\.nitter\.instance/.+(?:redirect_after_login=%2F(.+))`
|__Target__|`https://my.nitter.instance/$1`
|__Type__|RegEx
|__Notes__|Make sure to replace the `my.nitter.instance` part of the pattern and target with the domain from the instance you want to use.

## No old Reddit
> Redirect Old Reddit links to New Reddit

|||
|-|-
|__Example__|[https://old.reddit.com/r/subreddit/comments/post_id/post_title/](https://old.reddit.com/r/subreddit/comments/post_id/post_title/)
|__Pattern__|`https?://old\.reddit\.com/(.+)`
|__Target__|`https://www.reddit.com/$1`
|__Type__|RegEx

## High quality Reddit media
> Redirect and clean media URLs from Reddit

|||
|-|-
|__Example__|[https://preview.redd.it/1234567890.png?param1=0&param2=0&s=1234567890](https://preview.redd.it/1234567890.png?param1=0&param2=0&s=1234567890)
|__Pattern__|`https?://(?:preview\|i)\.redd\.it/(.+)\.(.{3,4})\?.+(s=.+)`
|__Target__|`https://i.redd.it/$1.$2?$3`
|__Type__|RegEx
|__Exclude__|`https?://(?:preview\|i)\.redd\.it/(.+)\.(.{3,4})\?.+(format=pjpg)(?:.+)?`
|__Notes__|If you are logged into Reddit you might need to remove `(s=.+)` from the pattern and `?$3` from the target

## Wikipedia-2-Wikiwand
> Redirect Wikipedia articles to Wikiwand

|||
|-|-
|__Example__|[https://en.wikipedia.org/wiki/the-article-you-want-to-read](https://en.wikipedia.org/wiki/the-article-you-want-to-read)
|__Pattern__|`https?://(.+)\.wikipedia\.org/wiki/(.+)`
|__Target__|`https://www.wikiwand.com/$1/$2`
|__Type__|RegEx
|__Exclude__|`https?://(.+)\.wikipedia\.org/wiki/(.+)\?oldformat=true`
|__Notes__|Append `?oldformat=true` to the URL to disable redirection.

## No Wikiwand mobile
> Fix Wikiwand mobile redirects

|||
|-|-
|__Example__|[https://www.wikiwand.com/en.m/the-article-you-want-to-read](https://www.wikiwand.com/en.m/the-article-you-want-to-read)
|__Pattern__|`https?://www\.wikiwand\.com/(.+)\.m/(.+)`
|__Target__|`https://www.wikiwand.com/$1/$2`
|__Type__|RegEx

## High quality Discord media
> Clean media URLs from the Discord CDN

|||
|-|-
|__Example__|[https://cdn.discordapp.com/type/1234567890.jpg?param1=0&param2=0](https://cdn.discordapp.com/type/1234567890.jpg?param1=0&param2=0)
|__Pattern__|`https?://cdn\.discordapp\.com/(.+)/(.+)\.(.{3,4})\?.+`
|__Target__|`https://cdn.discordapp.com/$1/$2.$3`
|__Type__|RegEx
|__Notes__|In theory, you could set the pattern to apply to `Images` so that every image inside Discord is fetched at its highest quality.

## High quality Steam Workshop media
> Clean media URLs from the Steam Workshop CDN

|||
|-|-
|__Example__|[https://steamuserimages-a.akamaihd.net/ugc/1234567890/1234567890/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true](https://steamuserimages-a.akamaihd.net/ugc/1234567890/1234567890/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true)
|__Pattern__|`https?://steamuserimages-a\.akamaihd\.net/ugc/(.+)/(.+)/.+`
|__Target__|`https://steamuserimages-a.akamaihd.net/ugc/$1/$2/`
|__Type__|RegEx
|__Notes__|Apply this to `Images` if you want high quality previews|

## 403 pximg fix
> Redirect i.pximg.net URLs to the Pixiv post

|||
|-|-
|__Example__|[https://i.pximg.net/img-original/img/1234/12/12/12/12/12/1234567890_p0.png](https://i.pximg.net/img-original/img/1234/12/12/12/12/12/1234567890_p0.png)
|__Pattern__|`https?://i\.pximg\.net/.+/(.+)_p.+`
|__Target__|`https://www.pixiv.net/en/artworks/$1`
|__Type__|RegEx
