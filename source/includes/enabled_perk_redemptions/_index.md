## [GET] List Enabled Perk Redemptions

```shell
curl "ENV_URL/api/v1/clients/enabled_perk_redemptions?app_id=APP_ID&date=2018-11-15"
  -X GET
  -H "Accept": "application/json"
  -H "Content-Type": "application/json"
  -H "Authorization": "Token token=ACCESS_TOKEN"
```
> The above command returns JSON structured like this:

```json
{
  "enabled_perk_redemptions": [
    {
      "id": "9ffb5c2c-5e65-4a03-bfaa-d06426222b2a",
      "client_identifier": "be8172a5-a51b-462d-816b-1ebc63ca0b95",
      "brand": "Amazon",
      "title": "5.0% off orders at Amazon",
      "value": 5000,
      "discount": 5.0,
      "money_saved": 250,
      "custom": false,
      "created_at": "2018-11-15T16:10:24.499Z"
    },
    {
      "id": "ff7df128-74f9-4a5b-a154-e574f823f705",
      "client_identifier": "be8172a5-a51b-462d-816b-1ebc63ca0b95",
      "brand": "Tesco",
      "title": "5.0% off at Tesco",
      "value": 10000,
      "discount": 5.0,
      "money_saved": 500,
      "custom": false,
      "created_at": "2018-11-15T16:10:24.506Z"
    }
  ],
  "metadata": {
    "total_records": 2,
    "continuation_token": null
  }
}
```

This endpoint returns up to 50 perk redemptions per request for a given date. Subsequent pages of results can be retrieved by repeating the request and passing in a continuation token, received in the previous response.


Parameter | Description
--------- | -----------
ACCESS_TOKEN | Your application's active access token [required]
app_id | Your application's app id [required]
date | A date string in the format YYYY-MM-DD to retrieve perk redemptions [required]
continuation_token | The token returned by the previous request, if retrieving a subsequent page of results [optional]