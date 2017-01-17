# Presearch

## The presearch resource

Presearch API is useful for showing summarized content of specific post IDs.

`GET https://live-community-e2e.platform.intuit.com/v2/shared/presearch`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/presearch?ids=1,4,2" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "Cache-Control: no-cache" \
```

> The above command returns a JSON structured like this:

```json
{
  "presearch": [
    {
      "id": 1,
      "created_at": "2016-08-18T06:28:17Z",
      "updated_at": "2017-01-06T19:50:40Z",
      "url": "https://live-community-e2e.platform.intuit.com/questions/1",
      "subject": "Beard sustainable mlkshk kale chips farm-to-table intelligentsia try-hard etsy, 8-bit tofu lo-fi actually",
      "summary_extraction": "Dolores autem omnis. Dicta eius vero omnis qui. Cum illum dolore voluptate labore. Saepe libero debitis. Atque blanditiis iure aut optio. Expedita similique quo voluptates quo autem fuga. Distinctio voluptatem ut repellat."
    },
    {
      "id": 4,
      "created_at": "2016-08-18T06:28:17Z",
      "updated_at": "2016-08-18T06:28:34Z",
      "url": "https://live-community-e2e.platform.intuit.com/questions/4",
      "subject": "Chartreuse marfa squid, occupy gastropub lumbersexual beard pour-over green juice fap offal health goth chambray",
      "summary_extraction": "Voluptatem distinctio labore minima. Sint commodi quibusdam distinctio. Provident non voluptatum nihil aut. Facere ipsa occaecati. Nam ad magnam debitis. Officia repellat aspernatur vitae commodi."
    },
    {
      "id": 2,
      "created_at": "2016-08-18T06:28:17Z",
      "updated_at": "2017-01-06T19:50:40Z",
      "url": "https://live-community-e2e.platform.intuit.com/questions/2",
      "subject": "Messenger bag YOLO chicharrones, humblebrag single-origin coffee pork belly marfa umami PBR&amp;B chambray",
      "summary_extraction": "Debitis qui id. Harum eum iure voluptatibus. In reprehenderit eos dignissimos nobis enim eligendi optio. Qui corrupti voluptate consequuntur fuga deleniti labore explicabo. Sint veniam qui rerum perspiciatis et. Qui quos commodi et modi et. Except..."
    }
  ]
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
id | Integer | The ID of the resource, provided in order of the query `ids`.
created_at | Datetime (iso8601) | The timestamp of which the resource was created.
updated_at | Datetime (iso8601) | The timestamp of which the resource last changed.
url | String | Canonical url of the resource.
subject | String | The subject text of the resource.
summary_extraction | String | The summarized context of the body of the resource.

### URL parameters

Parameter | Description
--------- | -----------
ids | A comma delimited list of ids
