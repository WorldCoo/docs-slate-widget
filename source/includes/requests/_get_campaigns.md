## Get available NGO Campaigns

> Example of ngo campaigns call:

```shell
curl -X POST
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ etc...
```

> Response:

```json
{
  "items": [
    {
        "id": "8720fdd5-1b10-a4c8-a614-d437667dcea9",
        "name": " NGO Name Example 1",
        "campaigns": [
            {
                "id": "a9fb530d-6270-0cc7-e8a8-84f3aab8478a",
                "name": "NGO Campaign 1",
                "status": "opened",
                "related_media": [
                     {
    	      "1": "http://cdn.worldcoo.com/ngos/8720fdd5-1b10-a4c8-a614-d437667dcea9/campaign/a9fb530d-6270-0cc7-e8a8-84f3aab8478a/1.png",
    	      "2": "http://cdn.worldcoo.com/ngos/8720fdd5-1b10-a4c8-a614-d437667dcea9/campaign/ a9fb530d-6270-0cc7-e8a8-84f3aab8478a/2.png",
    	      "3": "http://cdn.worldcoo.com/ngos/8720fdd5-1b10-a4c8-a614-d437667dcea9/campaign/ a9fb530d-6270-0cc7-e8a8-84f3aab8478a/3.png "
                     }],
                "description": "This is an example of campaign description.",
    			"location": [
    			 {
    			      "country": [{
    		           	         "code": "ESP",
    		                     "name": "Spain"
    		       	    }],
    		       	    "city": "Cáceres"
    			 }],
                "category": "children",
                "currency": "EUR",
                "budget": [
                     {
    	      "total": "100000",
    	      "transport": "50000",
    	      "materials": "10000",
    	      "providers": "35000",
    	      "team": "5000"
                     }],
                "current_funding": "3527",
                "current_donor_qty": "3212",
                "beneficiaries": "1500",
                "starting_date": "1464277166",
                "ending_date": ""
            },
            {
                "id": "6ef093ae-c9e0-f79f-ffe0-2953c7eb51c9",
                "name": "NGO Campaign 2",
                "status": "opened",
                "related_media": [
                     {
    	      "1": "http://cdn.worldcoo.com/ngos/8720fdd5-1b10-a4c8-a614-d437667dcea9/campaign/ 6ef093ae-c9e0-f79f-ffe0-2953c7eb51c9/1.png",
    	      "2": " http://cdn.worldcoo.com/ngos/8720fdd5-1b10-a4c8-a614-d437667dcea9/campaign/ 6ef093ae-c9e0-f79f-ffe0-2953c7eb51c9/2.png"
                     }],
                "description": "This is an example of campaign description.",
                "location": [
    	 {
    	      "country": [{
               	         "code": "FRA",
                         "name": "France"
           	    }],
           	    "city": "Paris"
    	 }],
                "category": "health",
                "currency": "EUR",
                "budget": [
                     {
    	      "total": "100000",
    	      "transport": "50000",
    	      "materials": "10000",
    	      "providers": "35000",
    	      "team": "5000"
                     }],
                "current_funding": "2452",
                "current_donor_qty": "2232",
                "beneficiaries": "1500",
                "starting_date": "1464277166",
                "ending_date": ""
            }]
    }
  ],
  "total": 105,
  "offset": 0,
  "limit": 1
}

```

`GET https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns`

### HTTP Headers

Header name | Required | default | Description
---------- | ------- | ------- | -------
Authorization | yes | NA | Authorization token provided by WorldCoo
[Accept-Language](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4) | No | en | iso 639-2/b language code.

### Query params

Param name | Required | default | Description
---------- | ------- | ------- | -------
offset | no | 0 | The amount of items to ignore.
limit | no | 20 | The maximum number of items to return.