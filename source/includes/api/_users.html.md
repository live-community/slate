# User

## The user resource

```json
{
  "id":946995,
  "created_at":"2013-09-26T21:12:31Z",
  "updated_at":"2016-10-31T19:08:04Z",
  "url":"https://community.intuit.com/users/946995",
  "display_name":"IntuitLauraB",
  "role":"Employee SuperUser",
  "title":"QBO Service and Support Rep",
  "questions_count":0,
  "comments_count":7,
  "discussions_count":0,
  "answers_count":26,
  "discussion_replies_count":0,
  "replies_count":0,
  "avatars":{
    "tiny":"https://d2gcv4sxt84gxu.cloudfront.net/uploads/avatars/946995/tiny.png?1383444120",
    "thumb":"https://d2gcv4sxt84gxu.cloudfront.net/uploads/avatars/946995/thumb.png?1383444120",
    "small":"https://d2gcv4sxt84gxu.cloudfront.net/uploads/avatars/946995/small.png?1383444120"
  }
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
id | Integer | The unique identifier of the user.
created_at | Datetime (iso8601) | The timestamp of which the resource was created.
updated_at | Datetime (iso8601) | The timestamp of which the resource last changed.
url | String | URL of the user.
display_name | String | The display name of the users.
role | String | The role the user belongs to.
title | String | the title of the user.
questions_count | Integer | The number of questions the user has created.
comments_count | Integer | The number of comments the user has created.
discussions_count | Integer | The number of discussions the user has created.
answers_count | Integer | The number of answers the user has created.
discussion_replies_count | Integer | The number of discussion replies the user has created.
replies_count | Integer | The number of replies the user has created.
avatars | Object | The image URL of the users' avatar in different sizes.
