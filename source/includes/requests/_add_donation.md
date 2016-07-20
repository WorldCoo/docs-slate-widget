## Add donation

> Example of add donation call:

```shell
curl -X POST
-H "Authorization: <ACCESS_TOKEN>"
-H "content-type: application/json"
https://api.worldcoo.com/v3/ngos/2454de2c-cb31-44e5-83bd/campaigns/a9fb530d-6270-0cc7-e8a8/donations
--data '{"amount": 5, "currency": "EUR", "order_code": "9638467"}'
```

> Example of add donation response:

```json
{
    "id": "17a10455-120d-e767-0206",
    "amount": 5,
    "currency": "EUR",
    "order_code": "9638467"
}
```

`POST https://api.worldcoo.com/v3/ngos/{{ngo_id}}/campaigns/{{campaign_id}}/donations`

### Request

#### HTTP Headers

Header name | Required | default | Description
---------- | ------- | ------- | -------
Authorization | yes | NA | Authorization token provided by WorldCoo
[Accept-Language](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4) | No | en | iso 639-2/b language code.

#### Body

- **amount** *number*
- **currency** *[CurrencyCode](#currency-standar)*
- **order_code** *string*: Internal client reference regarding this donation

### Response

`201 Created`

##### Body
- **id** *string*
- **amount** *number*
- **currency** *[CurrencyCode](#currency-standar)*
- **order_code** *string*