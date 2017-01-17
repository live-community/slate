---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://answers.lc.intuit.com/tags/live%20community%20api%20v2'>Community</a>
  - <a href='https://devinternal.intuit.com/' target='_blank'>Services Portal</a>

includes:
  - api/search
  - api/autosuggest
  - api/presearch
  - api/questions
  - api/articles
  - api/products
  - api/answers
  - api/comments
  - api/users
  - api/votes
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
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123" \
  --header "Intuit_IAM_Authentication intuit_appid=YOUR_APP_ID,intuit_app_secret=YOUR_SECRET"
```

## Specifing your Community
Because there is a single API endpoint for all communities, you must pass a header to specify the community the request is on behalf of.

This is done by setting the `X-LC-Community-Host` header to the host of your community.

For example, if your community url is https://answers.lc.intuit.com/ then you would set the header to just the **hostname** of the url: `answers.lc.intuit.com`.

<aside class="success">
<b>Note:</b> If your host is <code>ttlc.intuit.com</code> please use <code>https://live-community-e2e.platform.intuit.com/v2/<b>tax</b>/</code> instead for tax isolated communities.
</aside>

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123" \
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
  -H "Intuit_IAM_Authentication intuit_appid=YOUR_APP_ID,intuit_app_secret=YOUR_SECRET" \
  -H "X-LC-Community-Host: answers.lc.intuit.com" \
  -H "X-Intuit-Auth-ID: 123456789"
```
