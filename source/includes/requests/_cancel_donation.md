## Cancel donation

> Example of cancel donation call:

```shell
curl -X DELETE
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/2454de2c-cb31-44e5-83bd/campaigns/a9fb530d-6270-0cc7-e8a8/donations/17a10455-120d-e767-0206
```

> Example of cancel donation response:

```json
{
    "id": "17a10455-120d-e767-0206",
    "amount": 5,
    "currency": "EUR",
    "order_code": "9638467"
}
```

`DELETE https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns/{{campaign_id}}/donations/{{donation_id}}`

### Response

#### 200 Ok

##### Response body

- **id** *string*
- **amount** *number*
- **currency** *[CurrencyCode](#currency-standar)*
- **order_code** *string*