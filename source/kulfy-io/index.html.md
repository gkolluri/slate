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

# Kulfy IO APIs


## Create Keyboard

> The above command returns JSON structured like this:

```response
Example: https://api.kulfy.io/v1/kulfycloud/createKeyboard

```

Response Body
```json
{
  "product": "Kulfy IO",
  "version": 1,
  "result": true,
  "message": "success message",
  "config":{
    "id": "keyboard-id",
    "type":"web2",
    "content_type":["gif","video","image"],
    "clients":["web","ios","android"],
    "languages": ["Telugu","Hindi"],
    "account": "xploree",
    "api_endpoint":"https://api.kulfy.io",
    "cdn_endpoint":"https://media.kulfy.io",
    "kulfy_sdk_version": "1.0",
    "settings":{}
  }
}
```


This endpoint creates a unique keyboard ID and sends it in the response

### HTTP Request 


`POST https://api.kulfy.io/v1/kulfycloud/createKeyboard`

Request Body
```json
{
    "config":{
      "type":"web2",
      "content_type":["gif","video","image"],
      "clients":["web","ios","android"],
      "languages": ["Telugu","Hindi"],
      "account": "xploree"
   }
}

```



<aside class="success">
Remember — Add Kulfy API Key to all API's
</aside>


## Get SDK Configuration

> The above command returns JSON structured like this:

```response
Example: https://api.kulfy.io/v1/kulfycloud/getSDKConfiguration?kid=keyboardID

```

```json
{
    "product": "Kulfy IO",
    "version": 1,
    "result": true,
    "message": "success message",
    "config":{
      "api_endpoint":"https://api.kulfy.io",
      "cdn_endpoint":"https://media.kulfy.io"
      "settings":{}
   }
}
```

This endpoint retrieves configuration of the Kulfy SDK

### HTTP Request

`GET https://api.kulfy.io/v1/kulfycloud/getSDKConfiguration`

### Query Parameters

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
kid     |  |  | unique keyboard id


<aside class="success">
Remember — Add Kulfy API Key to all API's
</aside>




## Get Keyboard Configuration

> The above command returns JSON structured like this:

```response
Example: https://api.kulfy.io/v1/kulfycloud/getkeyboardConfiguration?kid=keyboardID

```

```json
{
    "product": "Kulfy IO",
    "version": 1,
    "result": true,
    "message": "success message",
    "config":{
      "id": "keyboard-id",
      "menu":{
        "displayMenu":true,
        "menuItems":["ABC","GIF","NFTs","Settings"]
        },
      "abc":{},
      "gif":{
        "langauge":["telugu"],
        "content":["gif"],
        "default_search_keyword":"trending",
        "default_list": [
           "Recent",
           "Favorite",
           "Trending",
           "Latest",
           "popular",
           "uploads"
          ],
        "concepts_list":[
           "heroes",
          "heroines",
          "prime",
          "netflix",
          "aha",
          "comedy",
          "movie",
          "relationships",
          "reactions",
          "politicians"
        ]
      },
      "nfts":{},
      "settings":{}
   }
}
```

This endpoint retrieves config of the client keyboard.

### HTTP Request 

`GET https://api.kulfy.io/v1/kulfycloud/getkeyboardConfiguration`

### Query Parameters

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
kid     |  |  | unique keyboard id

<aside class="success">
Remember — Add Kulfy API Key to all API's
</aside>

## Get Keyboard Concepts 

> The above command returns JSON structured like this:

```response
Example: https://api.kulfy.io/v1/kulfycloud/getConcepts?kid=keybaordID&language=telugu

at kulfy : https://api.kulfyapp.com/v5/concepts/getConcepts?l?kid=keybaordID&language=telugu

```

```json
{
    "product": "Kulfy IO",
    "version": 1,
    "result": true,
    "message": "success message",
    "data": [
        {
            "name": "Heroes",
            "concept": "heroes",
            "title": "Top Telugu Heroes GIFs from Tollywood in 2021 by Kulfy Users",
            "short": "Heroes of Tollywood",
            "cover": "https://media.kulfyapp.com/0HX46B/0HX46B-360.gif",
            "description": "GIFs, stickers and videos of movies your favorite actors",
            "language": [
                "TELUGU"
            ]
        },
        {
            "name": "Heroines",
            "concept": "heroines",
            "title": "Top Telugu Herioines in Tollywood in 2021 by Kulfy Users",
            "short": "Heroines of Tollywood",
            "cover": "https://media.kulfyapp.com/wQjJOE/wQjJOE-360.gif",
            "description": "GIFs stickers and videos of your favorite Actresses in Telugu",
            "language": [
                "TELUGU"
            ]
        }
    ]
}
```

This endpoint retrieves all concepts per language.

### HTTP Request

`GET https://api.kulfy.io/v1/kulfycloud/getConcepts`

### Query Parameters

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
kid     |  |  | unique keyboard id
language | telugu | telugu,tamil,malayalam,hindi |Lanaguages to search

<aside class="success">
Remember — Add Kulfy API Key to all API's
</aside>


## Get Categories by Concept

> The above command returns JSON structured like this:

```response
Example: https://api.kulfy.io/v1/kulfycloud/getCategories?kid=keybaordID&language=telugu&&concept=mobilebrands
or
at Kulfy : https://api.kulfyapp.com/V2/categories/getCategories?kid=keybaordID&language=telugu&&concept=mobilebrands

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

This endpoint retrieves all trending categories per concept with language preference.

### HTTP Request

`GET https://api.kulfy.io/v1/kulfycloud/getCategories`

### Query Parameters

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
kid     |  |  | unique keyboard id
language | telugu | telugu,tamil,malayalam,hindi |Lanaguages to search
concept | *mandatory | Concept that user want to lookup


<aside class="success">
Remember — Add Kulfy API Key to all API's
</aside>


## Get Trending Keywords (default categories)

> The above command returns JSON structured like this:

```response
Example: https://api.kulfy.io/v1/kulfycloud/getTrendingKeywords 

or

https://api.kulfyapp.com/V3/kulfy/getTrendingKeywords?kid=keybaordID&language=telugu&transliteration=en&client=ios

```

```json
{
    "product": "Kulfy IO",
    "version": 1,
    "result": true,
    "message": "Trending success message",
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

This endpoint retrieves default trending keywords per client.

### HTTP Request

`GET https://api.kulfy.io/v1/kulfycloud/getTrendingKeywords`

### Query Parameters

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
kid     |  |  | unique keyboard id

<aside class="success">
Remember — Add Kulfy API Key to all API's
</aside>

## Get Kulfys By Keyword


> The above command returns JSON structured like this:

```response

Example: https://api.kulfy.io/v1/kulfycloud/search?kid=keybaordID&keyword=trending&skip=0&limit=2&language=Telugu&content=gif

or

 https://partnerapis.kulfyapp.com/V3/gifs/search?kid=keybaordID&client=keyboard&keyword=trending&skip=0&limit=2&language=Telugu,Tamil&content=gif

```

```json
{
    "product": "Kulfy IO",
    "version": 1,
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

`GET https://api.kulfy.io/v1/kulfycloud/search`

Parameter | Default | Options |Description
--------- | ------- | ------- | -----------
keyword |  | |Set the keyword
kid     |  |  | unique keyboard id
content | gif,video | gif,video,audio,image,sticker| gif is recommended by default
language | telugu | telugu,tamil,malayalam,hindi |Lanaguages to search
sort | poular | popular or latest | Results sorted by favorites vs time
skip | 0 | | Enter a value to skip for pagination
limit | 25 |  | Enter a value to limit for pagination



