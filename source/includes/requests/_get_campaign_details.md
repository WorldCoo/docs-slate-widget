## Get campaign details

> Example of campaign details call:

```shell
curl -X GET
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/2454de2c-cb31-44e5-83bd-e663abd4eb26/campaigns/a9fb530d-6270-0cc7-e8a8-84f3aab8478a
```

> Response:

```json
{
  "id": "a9fb530d-6270-0cc7-e8a8-84f3aab8478a",
  "ngo_id": "2454de2c-cb31-44e5-83bd-e663abd4eb26",
  "name": "NGO Campaign 1",
  "description": "This is an example of campaign description.",
  "status": "opened",
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
  "current_funding": 3527,
  "current_donor_qty": 3212,
  "beneficiaries": 1500,
  "starting_date": 1464277166,
  "ending_date": null
}
```

`GET https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns/{{campaign_id}}`

### Request

#### HTTP Headers

Header name | Required | default | Description
---------- | ------- | ------- | -------
Authorization | yes | NA | Authorization token provided by WorldCoo
[Accept-Language](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4) | No | en | iso 639-2/b language code.

### Response

#### 200 Ok

##### Body

- **id** *string*
- **name** *string*
- **description** *string*
- **location**
    - **country_code** *[CountryCode](#country-standar)*
    - **city_name** *string*
- **[category](#capaign-categories)** *string*
- **ngo_id** *string*
- **[status](#campaign-status)** *string*
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
- **current_funding** *number*
- **current_donor_qty** *number*
- **beneficiaries** *number*
- **starting_date** *[Date](#date-standar) | null*
- **ending_date** *[Date](#date-standar) | null*
