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
user | Object | [User resource](#the-user-resource) of the user who created the question.
product | Object | [Product resource](#the-product-resource) of the question assigned to the product.
answers | Array | Array of [answer resources](#the-answer-resource) to the question.
commments | Array | Array of [comment resources](#the-comment-resource) to the question.
