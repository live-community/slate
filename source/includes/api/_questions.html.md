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
    "user":{
      "id":996671,
      "created_at":"2013-11-02T03:44:20Z",
      "updated_at":"2015-10-06T15:44:50Z",
      "url":"https://community.intuit.com/users/996671",
      "display_name":"zacharybuchanan",
      "role":"User",
      "title":"",
      "questions_count":1,
      "comments_count":0,
      "discussions_count":0,
      "answers_count":1,
      "discussion_replies_count":0,
      "replies_count":0,
      "avatars":{
        "tiny":"https://d2gcv4sxt84gxu.cloudfront.net/assets/default-user-avatars-tiny-9c7b71167024976b1e242bf4f73a3e0705c8d003e2f166fe7f2bb9a1b6b6c07f.png",
        "thumb":"https://d2gcv4sxt84gxu.cloudfront.net/assets/default-user-avatars-thumb-82246b1c45ae7ca201b3a4b3d1d21558169d12fc115127c4deae5d4e92e18e97.png",
        "small":"https://d2gcv4sxt84gxu.cloudfront.net/assets/default-user-avatars-small-d5efadcf497ea7b3d86c6f8d148d66633a29ce78fa8391af628adf32d9989354.png"
      }
    },
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
user | Object | User resource of the user who created the question.
product | Object | [Product resource](#the-product-resource) of the question assigned to the product.
answers | Array | Array of answers to the question.
commments | Array | Array of comments to the question.
