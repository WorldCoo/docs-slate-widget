## Add donation

> Example of add donation call:

```shell
curl -X POST
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ etc...
```

> Response:

```json
{
    "id": "17a10455-120d-e767-0206-dc6b4106acbb",
    "status": "sucess"
}
```

`POST https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns/{{campaign_id}}/donations`

Required parameters:

Parm | Type | Required | Description
---------- | ------- | ------- | -------
donation_amount | NUMERIC(10,4) | Yes | String |
currency | String | Yes | String | ISO 4271 currency code
order_code | String | Yes | String | Internal client reference regarding this donation