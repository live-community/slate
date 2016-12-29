# Comments

## The comment resource

```json
{
  "id":2368268,
  "created_at":"2014-03-02T20:54:12Z",
  "updated_at":"2014-03-02T20:54:12Z",
  "body":"It appears that when I enter GST on an expense it is going into GST payable as a negative number I assumed this is to indicate any balance in this account as a credit.  Why would GST from expenses go into this account?  Where is the GST ITC account and why doesn't it show up on the Balance Sheet?",
  "url":"https://community.intuit.com/replies/2368268",
  "user":{ }
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
id | Integer | The unique identifier of the answer.
created_at | Datetime (iso8601) | The timestamp of which the resource was created.
updated_at | Datetime (iso8601) | The timestamp of which the resource last changed.
body | String | Content of the answer in plain text.
url | String | URL of the comment.
user | Object | [User resource](#the-user-resource) of the user who created the question.
