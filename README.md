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
|__Pattern__|`https?:\/\/old\.reddit\.com\/(.+)`
|__Target__|`https://www.reddit.com/$1`
|__Type__|RegEx
