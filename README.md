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
|__Notes__|Append `?oldformat=true` to the URL to disable redirection
