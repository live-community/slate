# Questions

## The question resource

```json
{
  "question":{
    "id":1063916,
    "created_at":"2013-11-02T04:19:50Z",
    "updated_at":"2015-01-15T23:16:34Z",
    "url":"https://community.intuit.com/questions/1063916",
    "subject":"How do you record GST paid on expenses so that it shows up on the GST/HST report?",
    "details":"I am trying to figure out how to record GST paid on expenses so that I can claim it for a reimbursement later. ",
    "tags":"gst",
    "closed":false,
    "followers_count":3,
    "current_user_following":false,
    "user":{ },
    "product":{ },
    "answers":[ ],
    "comments":[ ]
  }
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
id | Integer | The unique identifier of the resource.
created_at | Datetime (iso8601) | The timestamp of which the resource was created.
updated_at | Datetime (iso8601) | The timestamp of which the resource last changed.
url | String | Canonical url of the resource.
subject | String | The question text.
details | String | Additional details about the question.
tags | String (comma seperated list) | Categorization of the question.
closed | Boolean | Whether the question is closed for further answers and comments.
followers_count | Integer | Number of users following the question.
current_user_following | Boolean | Whether the current user is following this resource.
user | Object | [User resource](#the-user-resource) of the user who created the question.
product | Object | [Product resource](#the-product-resource) of the product assigned to the question.
answers | Array | Array of [answer resources](#the-answer-resource) to the question.
commments | Array | Array of [comment resources](#the-comment-resource) to the question.

## Retrieve a question

### HTTP Request

`GET https://live-community-e2e.platform.intuit.com/v2/shared/questions/<id>`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/768780" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0"
```

### URL Parameters

Parameter | Description
--------- | -----------
id | Unique identifier of the question.

### Response
A [question resource](#the-question-resource) object.

## Create a question

### HTTP Request

`POST https://live-community-e2e.platform.intuit.com/v2/shared/questions`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions" \
  -X POST \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "X-Intuit-Auth-ID: 12345" \
  -H "Cache-Control: no-cache" \
  -d '{"subject":"This is a question subject","details":"This is the details of the question","product_id":1000}'
```

> The above command returns a JSON structured like this: <br /> *This is just a summarized question resource.

```json
{
  "question": {
    "id": 123,
    "created_at": "2016-12-30T00:18:16Z",
    "updated_at": "2016-12-30T00:18:16Z",
    "url": "https://community.e2e.lc.a.intuit.com/questions/123",
    "subject": "This is the question subject",
    "details": "This is the details of the question",
    "tags":"",
    "closed":false,
    "followers_count":1,
    "current_user_following":true,
    "user":{
      "id":12345,
      "display_name":"test_user",
      "role":"User",
      "questions_count":1
    },
    "product":{
      "id":1000,
      "created_at":"2015-01-15T22:16:07Z",
      "updated_at":"2016-09-24T00:36:37Z",
      "name":"QuickBooks Online",
      "product_id":1000,
      "edition":"",
      "platform":"Online",
      "year":"",
      "group":"QuickBooks Online",
      "country":"United Kingdom"
    },
    "answers":[ ],
    "comments":[ ]
  }
}
```

### JSON body structure

Parameter | Description
--------- | -----------
subject<br><small>REQUIRED</small> | The question the user is asking. Must be between 15 and 255 characters.
details | Details about the question being asked.
product_id | The product_id of a product to be assigned to the question. Must be a valid product id.

### Response
A [question resource](#the-question-resource) object.


## Update a question

### HTTP Request

`PUT https://live-community-e2e.platform.intuit.com/v2/shared/questions/<id>`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123" \
  -X PUT \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "X-Intuit-Auth-ID: 12345" \
  -H "Cache-Control: no-cache" \
  -d '{"subject":"Everybody loves pizza!!","details":"This is the details of the question","product_id":1000}'
```

> The above command returns a JSON structured like this: <br /> *This is just a summarized question resource.

```json
{
  "question": {
    "id": 123,
    "created_at": "2016-12-30T00:18:16Z",
    "updated_at": "2016-12-30T00:18:16Z",
    "url": "https://community.e2e.lc.a.intuit.com/questions/123",
    "subject": "This is the question subject",
    "details": "This is the details of the question",
    "tags":"",
    "closed":false,
    "followers_count":1,
    "current_user_following":true,
    "user":{
      "id":12345,
      "display_name":"test_user",
      "role":"User",
      "questions_count":1
    },
    "product":{
      "id":1000,
      "created_at":"2015-01-15T22:16:07Z",
      "updated_at":"2016-09-24T00:36:37Z",
      "name":"QuickBooks Online",
      "product_id":1000,
      "edition":"",
      "platform":"Online",
      "year":"",
      "group":"QuickBooks Online",
      "country":"United Kingdom"
    },
    "answers":[ ],
    "comments":[ ]
  }
}
```

### JSON body structure

Parameter | Description
--------- | -----------
subject | The question the user is asking. Must be between 15 and 255 characters.
details | Details about the question being asked.
product_id | The product_id of a product to be assigned to the question. Must be a valid product id.

### Response
A [question resource](#the-question-resource) object.


## Delete a question

### HTTP Request

`DELETE https://live-community-e2e.platform.intuit.com/v2/shared/questions/<id>`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123" \
  -X DELETE \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "Cache-Control: no-cache" \
```

### Response
Head OK.


## Retrieve similar questions

This can be helpful to users who would like to see questions that are simliar to the one they are viewing.
A scenario would be when the question they're viewing isn't related to their needs, they might find something more useful with these results.

### HTTP Request

`GET https://live-community-e2e.platform.intuit.com/v2/shared/questions/<id>/similar`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123/similar" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "Cache-Control: no-cache" \
```

### Response
An array of [question resource](#the-question-resource) objects.


## Follow a question

Following a question allows the user to be notified of any new activities happening to the question. Such as new answers, new comments etc.

### HTTP Request

`POST https://live-community-e2e.platform.intuit.com/v2/shared/questions/<id>/follow`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123/follow" \
  -X POST \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "X-Intuit-Auth-ID: 12345" \
  -H "Cache-Control: no-cache" \
```

<aside class="notice">
To get a user to follow a question, pass in their Intuit Auth ID in the header.
</aside>

### Response
A [question resource](#the-question-resource) object.


## Unfollow a question

Unfollowing a question will stop the user from receiving notifications to the question. Sometimes when a question has already been answered and any further
discusions isn't helpful.

### HTTP Request

`DELETE https://live-community-e2e.platform.intuit.com/v2/shared/questions/<id>/unfollow`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/questions/123/unfollow" \
  -X DELETE \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "X-Intuit-Auth-ID: 12345" \
  -H "Cache-Control: no-cache" \
```

<aside class="notice">
To get a user to unfollow a question, pass in their Intuit Auth ID in the header.
</aside>

### Response
Head OK.
