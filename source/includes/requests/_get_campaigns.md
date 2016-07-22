## Get available campaigns

> Example of ngo campaigns call:

```shell
curl -X POST
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/v3/ngos/2454de2c-cb31-44e5-83bd/campaigns?limit=1
```

> Example of get campaigns response:

```json
{
  "items": [
    {
      "id": "a9fb530d-6270-0cc7-e8a8",
      "ngo_id": "2454de2c-cb31-44e5-83bd",
      "name": "NGO Campaign 1",
      "description": "This is an example of campaign description.",
      "status": "active",
      "location": [
        {
          "country": "ESP",
          "name": "Spain"
        }
      ],
      "category": "children",
      "currency": "EUR",
      "budget": {
        "total": 100000,
        "transport": 50000,
        "materials": 10000,
        "providers": 35000,
        "team": 5000
      },
      "beneficiaries": 1500,
      "starting_date": 1464277166,
      "ending_date": null,
      "counters": {
          "donations": 1,
          "donated": 48
      }
    }
  ],
  "total": 105,
  "offset": 0,
  "limit": 1
}

```

`GET https://api.worldcoo.com/v3/ngos/{{ngo_id}}/campaigns`

### Request

#### HTTP Headers

Header name | Required | default | Description
---------- | ------- | ------- | -------
Authorization | yes | NA | Authorization token provided by WorldCoo
[Accept-Language](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4) | No | en | iso 639-2/b language code.

#### Query params

Param name | Required | default | Description
---------- | ------- | ------- | -------
offset | no | 0 | The amount of items to ignore.
limit | no | 20 | The maximum number of items to return.

### Response

`200 Ok`

##### Response body

- **total** *number*
- **offset** *number*
- **limit** *number*
- **items** *(list)*
    - **id** *string*
    - **name** *string*
    - **description** *string*
    - **location**
        - **country_code** *[CountryCode](#country-standar)*
        - **city_name** *string*
    - **[category](#campaign-categories)** *string*
    - **ngo_id** *string*
    - **[status](#campaign-statuses)** *string*
    - **languages** *[LanguageCode](#language-standar) list*
    - **currency** *[CurrencyCode](#currency-standar)*
    - **budget**
        - **funding** *number*
        - **others** *number*
        - **transport** *number*
        - **materials** *number*
        - **providers** *number*
        - **team** *number*
        - **initial_funding** *number*
        - **other_donations** *number*
        - **donations_in_ecommerce** *number*
        - **amount_in_ecommerce** *number*
    - **beneficiaries** *number*
    - **starting_date** *[Date](#date-standar) | null*
    - **ending_date** *[Date](#date-standar) | null*
    - **counters**
        - **donations** *number*. Number of donations received.
        - **donated** *number*. Amount received expressed in EUR.