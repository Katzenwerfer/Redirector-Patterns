## No YouTube shorts
> Redirect YouTube shorts into normal video

|||
|-|-
|__Example__|[https://www.youtube.com/shorts/123456789](https://www.youtube.com/shorts/123456789)
|__Pattern__|`youtube\.com\/shorts\/(.+)`
|__Target__|`https://www.youtube.com/watch?v=$1`
|__Type__|RegEx

## Twitter-2-Nitter
> Redirect Twitter URLs to Nitter

|||
|-|-
|__Example__|[https://twitter.com/a_cool_user/status/123456789](https://twitter.com/a_cool_user/status/123456789)
|__Pattern__|`twitter\.com\/(.+)/(.+)/(.+)`
|__Target__|`https://my.nitter.instance/$1/$2/$3`
|__Type__|RegEx
|__Notes__|Make sure to replace the `my.nitter.instance` part of the target with the domain from the instance you want to use.

## No old Reddit
> Redirect old Reddit links to new Reddit

|||
|-|-
|__Example__|[https://old.reddit.com/r/subreddit/comments/post_id/post_title/](https://old.reddit.com/r/subreddit/comments/post_id/post_title/)
|__Pattern__|`old\.reddit\.com\/(.+)`
|__Target__|`https://www.reddit.com/$1`
|__Type__|RegEx

## High quality Reddit CDN
> Redirect preview.redd.it links to i.redd.it
>
> Also removes any extra parameters the URL may have

|||
|-|-
|__Example__|[https://preview.redd.it/1234567890.png?param1=0&param2=0&param3=0](https://preview.redd.it/1234567890.png?param1=0&param2=0&param3=0)
|__Pattern__|`preview\.redd\.it\/(.+)\.(.{3,4})\?`
|__Target__|`https://i.redd.it/$1.$2`
|__Type__|RegEx

## Wikipedia-2-Wikiwand
> Redirect Wikipedia articles to the Wikiwand website

|||
|-|-
|__Example__|[https://en.wikipedia.org/wiki/the-article-you-want-to-read](https://en.wikipedia.org/wiki/the-article-you-want-to-read)
|__Pattern__|`\/\/(.+)\.wikipedia\.org\/wiki\/(.+)`
|__Target__|`https://www.wikiwand.com/$1/$2`
|__Type__|RegEx
|__Exclude__|`https?:\/\/(.*)\.wikipedia\.org\/wiki\/(.*)\?(oldformat=true)`
|__Notes__|Append `?oldformat=true` to the URL to disable redirection.

## No Wikiwand mobile
> Fix Wikiwand mobile redirects

|||
|-|-
|__Example__|[https://www.wikiwand.com/en.m/the-article-you-want-to-read](https://www.wikiwand.com/en.m/the-article-you-want-to-read)
|__Pattern__|`wikiwand\.com\/(.+)\.m\/(.+)`
|__Target__|`https://www.wikiwand.com/$1/$2`
|__Type__|RegEx

## High quality Discord CDN
> Force fetch of high quality images from the Discord CDN 

|||
|-|-
|__Example__|[https://cdn.discordapp.com/type/1234567890.jpg?param1=0&param2=0](https://cdn.discordapp.com/type/1234567890.jpg?param1=0&param2=0)
|__Pattern__|`cdn\.discordapp\.com\/(.+)\/(.+)\.(.{3,4})`
|__Target__|`https://cdn.discordapp.com/$1/$2.png`
|__Type__|RegEx
|__Notes__|In theory, you could set the pattern to apply to images so that every image inside Discord is fetched at its highest quality.

## HQ Steam Workshop previews
> Force fetch of high quality image previews for Steam Workshop pages

|||
|-|-
|__Example__|[https://steamuserimages-a.akamaihd.net/ugc/0123456789/0123456789/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true](https://steamuserimages-a.akamaihd.net/ugc/0123456789/0123456789/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true)
|__Pattern__|`steamuserimages-a\.akamaihd\.net\/ugc\/(.+)\/(.+)\/`
|__Target__|`https://steamuserimages-a.akamaihd.net/ugc/$1/$2/?imw=1920&ima=fit&impolicy=Letterbox`
|__Type__|RegEx
|__Notes__|Ideally, this pattern should be set for images only.

## HQ Steam Workshop image URLs
> Remove parameters from Steam Workshop image URLs

|||
|-|-
|__Example__|[https://steamuserimages-a.akamaihd.net/ugc/0123456789/0123456789/?imw=512&imh=512&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true](https://steamuserimages-a.akamaihd.net/ugc/0123456789/0123456789/?imw=512&imh=512&ima=fit&impolicy=Letterbox&imcolor=#000000&letterbox=true)
|__Pattern__|`steamuserimages-a\.akamaihd\.net\/ugc\/(.+)\/(.+)\/`
|__Target__|`https://steamuserimages-a.akamaihd.net/ugc/$1/$2/`
|__Type__|RegEx
