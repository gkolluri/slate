---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - response

toc_footers:
  - <a href='mailto:namaste@kulfyapp.com'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kulfy API
---

# Introduction

Welcome to the [Kulfy IO](https://beta.kulfy.io/) API! You can use our API to access Kulfy Keboard API endpoints, which can get information on Keyboard configuration and service APIs.


# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "apikey: meowmeowmeow"
```


> Make sure to replace `meowmeowmeow` with your API key.

Kulfy uses API keys to allow access to the API. You can email us at [namaste@kulfyapp.com](mailto:namaste@kulfyapp.com)  to request an API key.

Kulfy expects for the API key to be included in all API requests to the server in a header that looks like the following:

`apikey: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Search

## Get Trending Keywords

> The above command returns JSON structured like this:

```response
Example: https://partnerapis.kulfyapp.com/V3/kulfy/getTrendingKeywords?language=Telugu&transliteration=en&client=web

```

```json
{
    "product": "Kulfy App",
    "version": 2,
    "result": true,
    "message": "Trending success message",
    "trending_words_en": [
        "Trending",
        "lists",
        "RRR",
        "Latest",
        "popular",
        "uploads",
        "test",
        "ipl",
        "thankyou",
        "devotional",
        "sticker",
        "dialogues",
        "dance",
        "actor",
        "actress",
        "attitude",
        "text",
        "reactions",
        "girls",
        "animation"
    ],
    "trending_words": [
        "Trending",
        "lists",
        "RRR",
        "Latest",
        "popular",
        "uploads",
        "test",
        "ipl",
        "thankyou",
        "devotional",
        "sticker",
        "dialogues",
        "dance",
        "actor",
        "actress",
        "attitude",
        "text",
        "reactions",
        "girls",
        "animation"
    ]
}
```

This endpoint retrieves all trending keywords per language.

### HTTP Request

`GET https://partnerapis.kulfyapp.com/V3/kulfy/getTrendingKeywords`

### Query Parameters

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
language | telugu | telugu,tamil,malayalam,hindi |Lanaguages to search
transliteration | en | en|Currenlty only english is supported
client | web | web or keyboard | select clients 

<aside class="success">
Remember — Added Kulfy API Key to all API's
</aside>

## Get Kulfys By Keyword


> The above command returns JSON structured like this:

```response
Example: https://partnerapis.kulfyapp.com/V3/gifs/search?client=keyboard&keyword=trending&skip=0&limit=2&language=Telugu,Tamil&content=gif

```

```json
{
    "product": "Kulfy App",
    "version": 3,
    "default_gif": "",
    "share_message": "",
    "no_results_gif": "https://media2.giphy.com/media/tAS9GGJfEYL5e/giphy.webp",
    "results_count": 10000,
    "data": [
        {
            "content_type": "gif",
            "height": "1080",
            "width": "1080",
            "name_en": "Romeo Juliet",
            "category_en": [
                "ghani",
                "romeo juliet",
                "song",
                "dance",
                "saiee manjrekar",
                "dancing",
                "actress gifs",
                "gif",
                "best gifs",
                "hd gifs",
                "ghani movie gifs",
                ""
            ],
            "name": "Romeo Juliet",
            "category": [
                "ghani",
                "romeo juliet",
                "song",
                "dance",
                "saiee manjrekar",
                "dancing",
                "actress gifs",
                "gif",
                "best gifs",
                "hd gifs",
                "ghani movie gifs",
                ""
            ],
            "kulfy_id": "38X0CC",
            "sticker_url": "https://media.kulfyapp.com/38X0CC/38X0CC-sticker.webp",
            "image_url": "https://media.kulfyapp.com/38X0CC/38X0CC-sticker.webp",
            "gif_url": "https://media.kulfyapp.com/38X0CC/38X0CC-360.gif",
            "video_url": "https://media.kulfyapp.com/38X0CC/38X0CC.mp4",
            "share_url": "https://media.kulfyapp.com/38X0CC/38X0CC-shared.gif",
            "video_share_url": "https://media.kulfyapp.com/38X0CC/38X0CC.mp4",
            "deeplink": "https://kulfyapp.com/kulfy/38X0CC"
        },
        {
            "content_type": "gif",
            "height": "1080",
            "width": "1080",
            "name_en": "Saiee Manjrekar Romeo Juliet Step",
            "category_en": [
                "ghani",
                "romeo juliet",
                "song",
                "dance",
                "saiee manjrekar",
                "dancing",
                "actress gifs",
                "trending",
                "gif",
                "best gifs",
                "hd gifs",
                "ghani movie gifs",
                ""
            ],
            "name": "Saiee Manjrekar Romeo Juliet Step",
            "category": [
                "ghani",
                "romeo juliet",
                "song",
                "dance",
                "saiee manjrekar",
                "dancing",
                "actress gifs",
                "trending",
                "gif",
                "best gifs",
                "hd gifs",
                "ghani movie gifs",
                ""
            ],
            "kulfy_id": "38X0CB",
            "sticker_url": "https://media.kulfyapp.com/38X0CB/38X0CB-sticker.webp",
            "image_url": "https://media.kulfyapp.com/38X0CB/38X0CB-sticker.webp",
            "gif_url": "https://media.kulfyapp.com/38X0CB/38X0CB-360.gif",
            "video_url": "https://media.kulfyapp.com/38X0CB/38X0CB.mp4",
            "share_url": "https://media.kulfyapp.com/38X0CB/38X0CB-shared.gif",
            "video_share_url": "https://media.kulfyapp.com/38X0CB/38X0CB.mp4",
            "deeplink": "https://kulfyapp.com/kulfy/38X0CB"
        }
    ],
    "message": "",
    "success": true
}
```

This endpoint retrieves Kulfys based on a keyword in a specified language.

### HTTP Request

`GET https://partnerapis.kulfyapp.com/V3/gifs/search`

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
keyword | '' | |Set the keyword
content | gif,video | gif,video,audio,image,sticker| gif is recommended by default
language | telugu | telugu,tamil,malayalam,hindi |Lanaguages to search
sort | poular | popular or latest | Results sorted by favorites vs time
skip | 0 | | Enter a value to skip for pagination
limit | 25 |  | Enter a value to limit for pagination
transliteration | en | en|Currenlty only english is supported
client | web | web or keyboard | select clients 
transliteration | en | en|Currenlty only english is supported


