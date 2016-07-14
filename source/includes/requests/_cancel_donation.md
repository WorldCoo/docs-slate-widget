## Cancel donation

> Example of cancel donation call:

```shell
curl -X POST
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ etc...
```

> Response:

```json
{
    "id": "17a10455-120d-e767-0206-dc6b4106acbb",
    "status": "removed"
}
```

`DEL https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns/{{campaign_id}}/donations/{{donation_id}}`

Required parameters:

Parm | Type | Required | Description
---------- | ------- | ------- | -------
- | - | - | - | -
