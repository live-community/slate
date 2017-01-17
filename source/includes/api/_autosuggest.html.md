# Autosuggest

## The autosuggest resource

Autosuggest API is an endpoint where we provide results returned from STS to show suggestive search results/queries that users have searched in the past, or what kind of content we have that shares similar queries.

`GET https://live-community-e2e.platform.intuit.com/v2/shared/autosuggest`

```shell
curl "https://live-community-e2e.platform.intuit.com/v2/shared/autosuggest?q=where" \
  -X GET \
  -H "X-LC-Community-Host: community.e2e.lc.a.intuit.com" \
  -H "Content-Type: application/json" \
  -H "Authorization: Intuit_APIKey intuit_apikey=akyreexample7oCKuUf, intuit_apkey_version=1.0" \
  -H "Cache-Control: no-cache" \
```

> The above command returns a JSON structured like this:

```json
{
  "autosuggest": [
    "wheres my refund",
    "where is my return",
    "where are my taxes",
    "where is my w2"
  ]
}
```

### Attributes

Name | Type | Description
--------- | ------- | -----------
autosuggest | Array | An array of strings for autosuggest queries

### URL parameters

Parameter | Description
--------- | -----------
q | The query
