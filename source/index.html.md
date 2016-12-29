---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://answers.lc.intuit.com/tags/live%20community%20api%20v2'>Community</a>
  - <a href='https://devinternal.intuit.com/' target='_blank'>Services Portal</a>

includes:
  - api/questions
  - errors

search: true
---

# Introduction

Welcome to the documentation for the Live Community V2 API. You can user our API to ask questions, vote up answers, and get similar questions.
You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

The code powering our API is internal open source so please feel free to poke around [the code](https://github.intuit.com/LiveCommunity/live_community).

# Getting Started

## On Boarding

Onboarding to the API is done via the Services Portal page for the [Live Community v2 API](https://devinternal.intuit.com/index.html#/main/doc/ljo2/overview).

## Authentication

When you onboard via the Services Portal you will receive the api hostname, app id, and app secret needed to make an authenticated API call.
You must set the Authentication header with:

`Intuit_IAM_Authentication intuit_appid=YOUR_APP_ID,intuit_app_secret=YOUR_SECRET`

<aside class="notice">
You must replace <code>YOUR_APP_ID</code> and <code>YOUR_SECRET</code> with the app id and app secret provided to you.
</aside>


> To authorize, use this code:

```shell
curl "https://api.qa.lc.a.intuit.com/api/v2/questions/123" \
  --header "Intuit_IAM_Authentication intuit_appid=YOUR_APP_ID,intuit_app_secret=YOUR_SECRET"
```

## Specifing your Community
Because there is a single API endpoint for all communities, you must pass a header to specify the community the request is on behalf of.

This is done by setting the `X-LC-Community-Host` header to the host of your community.

For example, if your community url is https://answers.lc.intuit.com/ then you would set the header to just the **hostname** of the url: `answers.lc.intuit.com`.

```shell
curl "https://api.qa.lc.a.intuit.com/api/v2/questions/123" \
  --header "X-LC-Community-Host: answers.lc.intuit.com"
```

## User Authorization
To make a request on behalf of a user, you must set the `X-Intuit-Auth-ID` header.

**Note:** this is not required for requests that don’t require an authenticate user to perform the action.

```shell
curl "https://api.qa.lc.a.intuit.com/api/v2/questions/123" \
  --header "X-Intuit-Auth-ID: 123456789"
```

## Putting it all together
Now you have all the pieces needed to make a successful call to the API.

```shell
curl "https://api.qa.lc.a.intuit.com/api/v2/questions/123" \
  --header "Intuit_IAM_Authentication intuit_appid=YOUR_APP_ID,intuit_app_secret=YOUR_SECRET"
  --header "X-LC-Community-Host: answers.lc.intuit.com"
  --header "X-Intuit-Auth-ID: 123456789"
```
# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

