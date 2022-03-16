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

Welcome to the [Kulfy](https://kulfyapp.com/) API! You can use our API to access Kulfy API endpoints, which can get information on various GIFs from different languages in our database.


# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```


> Make sure to replace `meowmeowmeow` with your API key.

Kulfy uses API keys to allow access to the API. You can email us at [namaste@kulfyapp.com](mailto:namaste@kulfyapp.com)  to request an API key.

Kulfy expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Search

## Get Trending Keywords

> The above command returns JSON structured like this:

```response
Example: https://gateway.kulfyapp.com/V3/kulfy/getTrendingKeywords?language=Telugu&transliteration=en&client=web

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

`GET https://gateway.kulfyapp.com/V3/kulfy/getTrendingKeywords`

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
Example: https://gateway.kulfyapp.com/V3/gifs/search?keyword=funny&skip=0&limit=2&language=Hindi&sort=latest&client=keyboard&content=gif

```

```json
{
    "product": "Kulfy App",
    "version": 3,
    "default_gif": "",
    "share_message": "",
    "no_results_gif": "https://media2.giphy.com/media/tAS9GGJfEYL5e/giphy.webp",
    "results_count": 428,
    "data": [
        {
            "content_type": "gif",
            "height": "1080",
            "width": "1080",
            "name_en": "A laugh in a minute",
            "category_en": [
                "ss rajamouli",
                "jakkanna",
                "laugh",
                "navvu",
                "smile",
                "laughter",
                "funny",
                "reaction",
                "expression",
                "joke",
                "chuckle",
                "burst",
                "gif",
                "trending",
                "crack up",
                "fun",
                "happy",
                ""
            ],
            "name": "A laugh in a minute",
            "category": [
                "ss rajamouli",
                "jakkanna",
                "laugh",
                "navvu",
                "smile",
                "laughter",
                "funny",
                "reaction",
                "expression",
                "joke",
                "chuckle",
                "burst",
                "gif",
                "trending",
                "crack up",
                "fun",
                "happy",
                ""
            ],
            "kulfy_id": "3C4CXO",
            "sticker_url": "https://media.kulfyapp.com/3C4CXO/3C4CXO-sticker.webp",
            "image_url": "https://media.kulfyapp.com/3C4CXO/3C4CXO-sticker.webp",
            "gif_url": "https://media.kulfyapp.com/3C4CXO/3C4CXO-360.gif",
            "video_url": "https://media.kulfyapp.com/3C4CXO/3C4CXO.mp4",
            "share_url": "https://media.kulfyapp.com/3C4CXO/3C4CXO-shared.gif",
            "video_share_url": "https://media.kulfyapp.com/3C4CXO/3C4CXO.mp4",
            "deeplink": "https://kulfyapp.com/kulfy/3C4CXO"
        },
        {
            "content_type": "gif",
            "height": "1080",
            "width": "1080",
            "name_en": "Is it",
            "category_en": [
                "radheshyam",
                "pooja hegde",
                "avuna",
                "is it",
                "true",
                "real",
                "ohh",
                "ok",
                "funny",
                "prabhas",
                "main ishq mein hoon",
                "uv creations",
                "darling",
                "rebelstar",
                "radhakrishnakumar",
                "manoj paramahamsa",
                "radhe shyam",
                "telugu best gifs",
                "hd gifs",
                "tollywood hq gifs",
                "telugu movie gifs",
                "panindia",
                "astrology",
                "vikramaditya",
                "palmist",
                "gif",
                "latest",
                ""
            ],
            "name": "Is it",
            "category": [
                "radheshyam",
                "pooja hegde",
                "avuna",
                "is it",
                "true",
                "real",
                "ohh",
                "ok",
                "funny",
                "prabhas",
                "main ishq mein hoon",
                "uv creations",
                "darling",
                "rebelstar",
                "radhakrishnakumar",
                "manoj paramahamsa",
                "radhe shyam",
                "telugu best gifs",
                "hd gifs",
                "tollywood hq gifs",
                "telugu movie gifs",
                "panindia",
                "astrology",
                "vikramaditya",
                "palmist",
                "gif",
                "latest",
                ""
            ],
            "kulfy_id": "3C4CX2",
            "sticker_url": "https://media.kulfyapp.com/3C4CX2/3C4CX2-sticker.webp",
            "image_url": "https://media.kulfyapp.com/3C4CX2/3C4CX2-sticker.webp",
            "gif_url": "https://media.kulfyapp.com/3C4CX2/3C4CX2-360.gif",
            "video_url": "https://media.kulfyapp.com/3C4CX2/3C4CX2.mp4",
            "share_url": "https://media.kulfyapp.com/3C4CX2/3C4CX2-shared.gif",
            "video_share_url": "https://media.kulfyapp.com/3C4CX2/3C4CX2.mp4",
            "deeplink": "https://kulfyapp.com/kulfy/3C4CX2"
        }
    ],
    "message": "",
    "success": true
}
```

This endpoint retrieves Kulfys based on a keyword in a specified language.

### HTTP Request

`GET https://gateway.kulfyapp.com/V3/gifs/search`

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


