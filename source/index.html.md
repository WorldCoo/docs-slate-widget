---
title: WorldCoo API Donation

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/WorldCoo/docs-slate-api/blob/master/source/index.html.md#donation-api-v3-overview' target='_blank'>See on Github</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

search: true
---

# Donation API V3 Overview

The WorldCoo Donation API offers web services that allow account customers to interact with WorldCoo systems and perform all the tasks required for them to send donations, as well as get data on NGOs and campaigns.

Built in accordance with industry standards, WorldCoo Donation API provides a simple and effective method for web and apps to integrate with WorldCoo and the NGO world, and and get started quickly. There are no costs to customers for using the WorldCoo Donation API services, but WorldCoo clients may incur their own development costs, which should be covered by the client.

WorldCoo will not accept any responsibility for any development, implementation and testing costs. Customers should address any inquiries regarding systems development to their account handler.


# Onboarding

Onboarding is a sandboxed test environment that allows you to test your integration without data being passed through to the WorldCoo operational systems. This ‘Onboarding’ environment is available 24/7, has the same functionality as live (though with a reduced capacity) and can be accessed using a special sandbox access / credentials provided to you during setup. You can access the environment via the following endpoint:

`https://sandbox.worldcoo.com/v3/`


# Live deployment

Once you have completed all the required testing in the onboarding environment you will be provided with access to the live production system. Please use the supplied Token ID to connect to this environment. 

The end point for the live WorldCoo Donation API web service is:

`https://api.worldcoo.com/v3/`


# API versioning

WorldCoo is continuously working to improve its technology, and as part of this process updates to the services provided may on occasion necessitate a new API version. WorldCoo will try to maintain three versions of the API as new versions are introduced, so that previous versions move down the stack until they are ultimately removed completely:

*	Latest version 
*	Previous version 
*	Deprecated version 

Customers will always be encouraged to integrate against the latest version as this will give them the longest stable period without the need to change, but if they have already begun integration activities when a new version is released then they will be able to integrate against the previous version. Customers should not integrate against the deprecated version.


# Authentication

## Only https connections allowed

Following international standards and with the aim of keeping our customers safe, the WorldCoo Donation API only allows SSL-encrypted communications.

## Authorization Header

> Example of authorized call:

```shell
curl -X POST 
-H "Content-type: application/json" 
-H "Authorization: Bearer <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ 
```

<aside class="success">
Prior to the Onboarding process, WorldCoo will provide you with a a set of credentials in order to interact with the API. 
</aside>
The WorldCoo Donation API uses token-based authentication with Authorization header following RFC 2617. All communications to this API must provide well-formed and active credentials. Any unauthorized access will result in 401 (Unauthorized) response code and further attempts may incur an automatic IP ban.

# Response Codes

<aside class="notice">This error section is stored in a separate file in `includes/_errors.md`. Slate allows you to optionally separate out your docs into many files...just save them to the `includes` folder and add them to the top of your `index.md`'s frontmatter. Files are included in the order listed.</aside>

The Kittn API uses the following error codes:


Error Code | Meaning
---------- | -------
200 | OK
201 | Created
202 | Accepted
301 | Moved permanently
302 | Found
400 | Bad request
401 | Unauthorized
403 | Forbidden
404 | Not Found
409 | Conflict, resource already exists
500 | Internal server error


# Requests


## Get available NGOs

> Example of ngo call:

```shell
curl -X POST 
-H "Content-type: application/json" 
-H "Authorization: Bearer <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ etc...
```

> Response:

```json
{
"ngos": [
        {
            "id": "8720fdd5-1b10-a4c8-a614-d437667dcea9",
            "name": "NGO Name Example 1",
            "url": "http://www.examplengo1.com",
            "logo": "http://cdn.worldcoo.com/ngo/8720fdd5-1b10-a4c8-a614-d437667dcea9/logos/logoexamplengo1.png",
            "description": "This is an example of NGO description."
        },
        {
            "id": "79a3b10a-3c84-a19a-5e07-12319c2bee6b",
            "name": "NGO Name Example 2",
            "url": "http://www.examplengo2.com",
            "logo": "http://cdn.worldcoo.com/ngo/79a3b10a-3c84-a19a-5e07-12319c2bee6b/logos/logoexamplengo2.png",
            "description": "This is an example of NGO description."
        }
]}
```

`GET https://api.worldcoo.com/ngos`

Required parameters:

Parm | Type | Required | Description
---------- | ------- | ------- | -------
lang | String | Yes | String | iso 639-2/b language code



## Get available NGO Campaigns

> Example of ngo campaigns call:

```shell
curl -X POST 
-H "Content-type: application/json" 
-H "Authorization: Bearer <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ etc...
```

> Response:

```json
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

```

`GET https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns`

Required parameters:

Parm | Type | Required | Description
---------- | ------- | ------- | -------
lang | String | Yes | String | iso 639-2/b language code




## Get campaign details

> Example of campaign details call:

```shell
curl -X POST 
-H "Content-type: application/json" 
-H "Authorization: Bearer <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/ etc...
```

> Response:

```json
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
        }
    ]
}
```

`GET https://api.worldcoo.com/ngos/{{ngo_id}}/campaigns/{{campaign_id}}`

Required parameters:

Parm | Type | Required | Description
---------- | ------- | ------- | -------
lang | String | Yes | String | iso 639-2/b language code




## Add donation

> Example of add donation call:

```shell
curl -X POST 
-H "Content-type: application/json" 
-H "Authorization: Bearer <ACCESS_TOKEN>"
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



## Cancel donation

> Example of cancel donation call:

```shell
curl -X POST 
-H "Content-type: application/json" 
-H "Authorization: Bearer <ACCESS_TOKEN>"
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
