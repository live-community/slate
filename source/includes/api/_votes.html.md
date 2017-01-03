# Votes

## The vote resource

```json
{
  "vote": {
    "id": 1547636,
    "created_at": "2017-01-03T18:29:59Z",
    "updated_at": "2017-01-03T18:29:59Z",
    "user_id": 5302444,
    "parent_id": 1250260,
    "parent_type": "Post",
    "direction": 1
  }
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
id | Integer | The unique identifier of the resource.
created_at | Datetime (iso8601) | The timestamp of which the resource was created.
updated_at | Datetime (iso8601) | The timestamp of which the resource last changed.
user_id | Integer | The user who owns this vote.
parent_id | Integer | The unique ID of the resource that is voted on.
parent_type | String | The type of resource that is voted on.
direction | Integer | The direction which the current user voted on the resource.<br />(1 for up vote, -1 for down vote)


## Create a vote

### HTTP Request

`POST https://live-community-e2e.platform.intuit.com/v2/shared/votes`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/votes" \
  -X POST \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0"
  -H "X-Intuit-Auth-ID: 12345"
  -d '{"parent_id":1250260,"parent_type":"Article","direction":1}'
```

### Form Parameters

Parameter | Description
--------- | -----------
parent_id<br><small>REQUIRED</small>  | The id of the resource to vote on.
parent_type<br><small>REQUIRED</small>  | The name of the resource to vote on (e.g. Question, Answer, Article).
direction<br><small>REQUIRED</small>  | `1` for an upvote or a `-1` for a downvote.
feedback | 255 character string containing feedback for the answer. This is only available on downvotes.

### Response
A [vote resource](#the-vote-resource) object.


## Update a vote

### HTTP Request

`PUT https://live-community-e2e.platform.intuit.com/v2/shared/votes/1547636`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/votes/1547636" \
  -X PUT \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0"
  -H "X-Intuit-Auth-ID: 12345"
  -d '{"feedback":"This is a test feedback"}'
```

### Form Parameters

Parameter | Description
--------- | -----------
feedback | 255 character string containing feedback for the answer. This is only available on downvotes.

### Response
A [vote resource](#the-vote-resource) object.
