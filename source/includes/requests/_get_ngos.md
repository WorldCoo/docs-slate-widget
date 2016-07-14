## Get available NGOs

> Example of ngo call:

```shell
curl -X GET
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos?limit=2&offset=10
```

> Example of get ngos response:

```json
{
    "items": [
            {
                "id": "8720fdd5-1b10-a4c8-a614",
                "name": "NGO Name Example 1",
                "url": "http://www.examplengo1.com",
                "logo": "http://cdn.worldcoo.com/ngo/8720fdd5-1b10-a4c8-a614-d437667dcea9/logos/logoexamplengo1.png",
                "description": "This is an example of NGO description."
            },
            {
                "id": "79a3b10a-3c84-a19a-5e07",
                "name": "NGO Name Example 2",
                "url": "http://www.examplengo2.com",
                "logo": "http://cdn.worldcoo.com/ngo/79a3b10a-3c84-a19a-5e07-12319c2bee6b/logos/logoexamplengo2.png",
                "description": "This is an example of NGO description."
            }
    ],
    "total": 53,
    "offset": 10,
    "limit": 2
}
```

`GET https://api.worldcoo.com/ngos`

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

#### 200 Ok

##### Response body

- **total** *number*
- **offset** *number*
- **limit** *number*
- **items** *list*
    - **id** *string*
    - **name** *string*
    - **url** *string*
    - **logo** *string*
    - **description** *string*