# Search

## The search results

```json
{
  "results": [
    {
      "title": "Why would I want a GoPayment credit card swiper (we call them “credit card readers”)?",
      "snippet": "First, a little background: Every time you accept a credit card, you pay what’s called a Discount fee  to the credit card company.",
      "url": "https://community.e2e.lc.a.intuit.com/content/p_sb_qbdt_us_iq_all_faq:GEN81854",
      "type": "Article",
      "type_id": 1250260,
      "type_attributes": {
        "id": 1250260,
        "created_at": "2015-10-30T16:26:47Z",
        "updated_at": "2017-01-03T18:50:42Z",
        "authored_at": "2015-10-30T16:26:47Z",
        "modified_at": "2016-12-30T20:16:50Z",
        "published_at": "2015-10-30T16:26:47Z",
        "up_votes_count": 4,
        "down_votes_count": 3,
        "content_identifier": "p_sb_qbdt_us_iq_all_faq:GEN81854",
        "author": {
          "id": 1,
          "name": "QuickBooks Help",
          "avatar_urls": [
            "https://d34t61rbkvnrz2.cloudfront.net/uploads/organizations/1/avatars/tiny.png?1445967884",
            "https://d34t61rbkvnrz2.cloudfront.net/uploads/organizations/1/avatars/thumb.png?1445967884",
            "https://d34t61rbkvnrz2.cloudfront.net/uploads/organizations/1/avatars/small.png?1445967884"
          ],
          "type": "Organization"
        }
      }
    }
  ],
  "meta": {
    "total_results": 151260,
    "total_pages": 15126,
    "current_page": 1,
    "per_page": 10,
    "facets": [
      {
        "name": "type",
        "param": "type",
        "label": "Type",
        "values": {
          "Article": 43524,
          "Question": 107680
        }
      }
    ]
  }
}
```

### Results attributes

Name | Type | Description
--------- | ------- | -----------
title | String | Title of the search results
snippet | String | Short snippet of the content that is helpful to user. (Could be a summary extraction of the best answer, a short snippet of the questions' details, or the summary of an articles' body)
url | String | The url of the search result resource.
type | String | The type of search result resource. (e.g. Question, Article, Discussion)
type_id | Integer | The unique identifier of the resource.
type_attributes | Object | Unique attributes to the type of the resource. This is a summary of attributes from the resource. It does <b>not</b> contain all of the attributes of the resource.

### Meta attributes

Name | Type | Description
--------- | ------- | -----------
total_results | Integer | The total number of results of the current search query. Useful for doing paginations.
total_pages | Integer | The number of pages based on per page configuration.
current_page | Integer | The current page number.
per_page | Integer | The number of results we show per page.
facets | Array | The facets that are returned with counts.


## Perform a search

`GET https://live-community-e2e.platform.intuit.com/v2/shared/search`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/search?q=*:*&facets[]=type&facets[]=product_name" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0"
  -H "Cache-Control: no-cache"
```

### URL parameters

Parameter | Description
--------- | -----------
q | The search query
page | The current page of the search results
per_page | The number of search results to show per page
facets | An array of facets to include in the response.<br />Available values: type, product_name, country.<br />The URL structure for array is `&facet[]=type&facet[]=product_name&facet[]=country`
tags | Search for content that are tagged with this value
product_slug | Filter the results by the provided product slug
product_name | Filter the results by the provided product name
product_edition | Filter the results by the provided product edition
product_platform | Filter the results by the provided product platform
document_type | Type of document to filter against. (Either `Question` or `Article`) can be filtered for now.
cc | Client context of the user. Refer to this [documentation](https://wiki.intuit.com/pages/viewpage.action?pageId=381981386) to understand what can be passed. To pass multiple context, pass as an array: `cc[Product_Type]=Online&cc[Product_Category]=free`.
