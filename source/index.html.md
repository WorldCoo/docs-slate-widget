---
title: WorldCoo API Donation

includes:
  - requests/get_ngos
  - requests/get_campaigns
  - requests/get_campaign_details
  - requests/add_donation
  - requests/cancel_donation

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
-H "Authorization: <ACCESS_TOKEN>"
https://api.worldcoo.com/ngos/
```

<aside class="success">
Prior to the Onboarding process, WorldCoo will provide you with a a set of credentials in order to interact with the API.
</aside>
The WorldCoo Donation API uses token-based authentication with Authorization header following RFC 2617. All communications to this API must provide well-formed and active credentials. Any unauthorized access will result in 401 (Unauthorized) response code and further attempts may incur an automatic IP ban.

# HTTP response codes

Response Code | Meaning
---------- | -------
200 | OK
201 | Created
202 | Accepted
301 | Moved permanently
302 | Found
400 | Bad request
401 | Unauthorized
404 | Not Found
500 | Internal server error

# Requests