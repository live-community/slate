# Articles

## The article resource

```json
{
  "article":{
    "id":1250260,
    "created_at":"2015-10-30T16:26:47Z",
    "updated_at":"2016-12-30T20:16:50Z",
    "authored_at":"2015-10-30T16:26:47Z",
    "modified_at":"2016-02-02T23:33:12Z",
    "published_at":"2015-10-30T16:26:47Z",
    "up_votes_count":4,
    "down_votes_count":3,
    "content_identifier":"p_sb_qbdt_us_iq_all_faq:GEN81854",
    "title":"Why would I want a GoPayment credit card swiper (we call them “credit card readers”)?",
    "body":"<div class=\"SECTION\">\n <p>First, a little background: <br /> Every time you accept a credit card, you pay what’s called a <strong>Discount fee </strong>to the credit card company. The rate of this discount fee varies according to the level of risk associated with accepting that card.<br /> <br /> If the card is “present” (meaning, you <em>“swipe” the card</em>), that’s considered a <strong>“qualified” sale </strong>(the theory is, you—the seller—are pretty sure the card is legitimate). <strong>This is the lowest discount rate you’ll pay for any qualified transaction.</strong> In some cases, when processing rewards cards, corporate cards or foreign cards you may pay a slightly higher non-qualified discount rate.<br /> <br /> If you <em>key the card number in</em>, that’s considered a <strong>“mid-qualified” sale</strong>, because it’s a little higher risk, since there’s no magnetic strip info that verifies that the card was present at the time of the sale. So—no surprise here: <strong>Higher risk, higher discount rate.  </strong><br /> <br /> If you’ve just signed up for GoPayment, your <strong>FREE card reader </strong>is on its way. It should get to you within 3-5 business days.</p>\n</div>\n<div class=\"OTHERARTICLESTOTRY\">\n <h2>Other Articles To Try</h2>\n <ul></ul>\n</div>",
    "product":null,
    "followers_count":0,
    "current_user_following":false,
    "url":"https://community.e2e.lc.a.intuit.com/articles/1250260-why-would-i-want-a-gopayment-credit-card-swiper-we-call-them-credit-card-readers",
    "author":{
      "id":1,
      "name":"QuickBooks Help",
      "avatar_urls":[
        "https://d34t61rbkvnrz2.cloudfront.net/uploads/organizations/1/avatars/tiny.png?1445967884",
        "https://d34t61rbkvnrz2.cloudfront.net/uploads/organizations/1/avatars/thumb.png?1445967884",
        "https://d34t61rbkvnrz2.cloudfront.net/uploads/organizations/1/avatars/small.png?1445967884"
      ],
      "type":"Organization"
    },
    "internal_details":null,
    "source":"inquira",
    "current_user_vote_direction":null,
    "current_user_vote_id":null
  }
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
id | Integer | The unique identifier of the resource.
created_at | Datetime (iso8601) | The timestamp of which the resource was created.
updated_at | Datetime (iso8601) | The timestamp of which the resource last changed.
authored_at | Datetime (iso8601) | The timestamp of which the content was originally written.
modified_at | Datetime (iso8601) | The timestamp of which the content was last modified.
published_at | Datetime (iso8601) | The timestamp of which the content was first published.
up_votes_count | Integer | The number of users who up voted this content.
down_votes_count | Integer | The number of users who down voted this content.
content_identifier | String | The global unique identifier of this article provided by STS.
title | String | The article title.
body | String | The body of the article. HTML safe.
product | Object | [Product resource](#the-product-resource) of the product assigned to the article.
followers_count | Integer | The number of users following this article.
current_user_following | Boolean | Whether the current user is following this resource.
url | String | The canonical url of this article.
author | Object | The author of this article. Usually an organization type.
internal_details | String | Returns an HTML safe of the internal details of the article if the user can view them.
source | String | The source name of where the article was authored in.
current_user_vote_direction | Integer | The direction which the current user voted on the resource.<br />(1 for up vote, -1 for down vote)
current_user_vote_id | Integer | The unique id of the vote resource of the current users' vote.


## Retrieve an article by ID

Retrieve an article by the ID.

<aside class="notice">
Live Community IDs of articles are not stable. Because we don't have
contol over article content, content writers can choose to archive and
write a new article, which generates a new ID for it. If you'd like a
more stable choice, please retrieve by content identifier.
</aside>

### HTTP Request

`GET https://live-community-e2e.platform.intuit.com/v2/shared/articles/<id>`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/articles/123" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0"
```

### URL Parameters

Parameter | Description
--------- | -----------
id | Unique identifier of the article.


## Retrieve by content identifier

Retrieve an article by its content identifier (Provided by STS team).

### HTTP Request

`GET https://live-community-e2e.platform.intuit.com/v2/shared/articles/by_content_identifier/<id>`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/articles/by_content_identifier/abc_123" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0"
```

### URL Parameters

Parameter | Description
--------- | -----------
id | STS global identifier of the article.
