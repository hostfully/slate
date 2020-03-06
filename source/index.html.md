---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - javascript
  - python

toc_footers:
  - <a href='https://v2.hostfully.com' target="_blank">Go to the Guidebook Platform</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

<!-- includes:
  - errors -->

search: true
---

# Getting Started

This page will help you get started with the Hostfully Guidebook Platform API. You'll be up and running in a jiffy!

### WELCOME TO THE HOSTFULLY GUIDEBOOK PLATFORM API!
This API is always under development. If you need help with implementing the API for your system, please contact us and we'll help you with your project.

If you notice the docs are out of date or are unclear, please don't be shy about letting us know.

### PREREQUISITES
Access to the Hostfully Guidebook Platform API is granted to users manually on a case to case basis. If you want to apply for API access please send an email with a description of your use case to support@hostfully.com.

### AUTHENTICATION
Authentication requires a Bearer Token, which can be acquired from a special API Access page in your Guidebook Platform Dashboard. You will need to include your key in every request made to the API. The API key has have to be provided as an HTTP request header called Authorization with the value ```Bearer {{token}}```

### STAGING VS PRODUCTION
We do have a staging (sandbox) environment you can use to develop your API connection. This documentation will focus on instructions for testing in this staging environment. When you're ready to move your implementation to production we'll help you out.

### RATE LIMIT
The Guidebook Platform has two rate limits:
500 calls within a 1 hour window per calling client (per IP address).
15 calls within a 1 minute window

Blacklisting
If a client application abuses the rate limits, it will be blacklisted. Blacklisted client apps are unable to get a response from the Hostfully API. If you or your application has been blacklisted and you think there has been a mistake, you can email us at support@hostfully.com to request assistance.

### SUPPORT AND FEEDBACK
Please feel free to send us suggestions or issues either through our Intercom channel or at support@hostfully.com.

# Authentication

> To authorize, use this code:


```shell
curl "api endpoint here"
  -H "authorization: Bearer {{token}}"
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("api endpoint here")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["authorization"] = 'Bearer {{token}}'

response = http.request(request)
puts response.read_body
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === this.DONE) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "api endpoint here");
xhr.setRequestHeader("authorization", "Bearer {{token}}");

xhr.send(data);
```

```python
import requests

url = "api endpoint here"

headers = {'authorization': 'Bearer {{token}}'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```


> Make sure to replace `{{token}}` with your actual API Token.

The Hostfully guidebook platform uses JWT bearer tokens to allow access to the API. 

Authentication requires a Bearer Token, which can be acquired from a special API Access page in your Guidebook Platform Dashboard. You will need to include your API Token in every request made to the API. 

The API key has have to be provided as an HTTP request header called `Authorization` with the value `Bearer {{token}}`

<aside class="notice">
You must replace <code>{{token}}</code> with your actual API Token.
</aside>

# Guidebooks

## GET /guidebooks/

```shell
curl "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/"
  -H "Authorization: Bearer {{token}}"
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://v2apistaging.hostfully.com/openapi/v1/guidebooks/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["authorization"] = 'Bearer {{token}}'

response = http.request(request)
puts response.read_body
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === this.DONE) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/");
xhr.setRequestHeader("authorization", "Bearer {{token}}");

xhr.send(data);
```

```python
import requests

url = "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/"

headers = {'authorization': 'Bearer {{token}}'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

> Make sure to replace `{{token}}` with your actual API Token.

> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "wifi": {
                "id": 22
            },
            "theme": null,
            "template": null,
            "secure_access_only": false,
            "recs_only_name": "",
            "recs_only_key": "pvhqfkq",
            "recs_only_image": "",
            "recs_only_enabled": false,
            "recommendations": [
                {
                    "key": "rkxzqtw",
                    "id": 12878
                }
            ],
            "parking": {
                "id": 17
            },
            "name": "Demo Guidebook",
            "key": "gkhlmxc",
            "is_template": false,
            "is_published": true,
            "informations": [
                {
                    "id": 157
                }
            ],
            "image": "https://cdn.filestackcontent.com/FJk3KmqQ6yl4QUe5nJgB",
            "id": 200804,
            "host_user_id": 201818,
            "host_intro": {
                "id": 39
            },
            "guidebooks": null,
            "directions": {
                "id": 17
            },
            "default_path": "",
            "checkout": {
                "id": 29
            },
            "checkin": {
                "id": 46
            },
            "address": {
                "timezone": "America/Chicago",
                "street_number": "214",
                "street_2": "",
                "street": "S Glover Ave",
                "state": "AL",
                "prefix": "",
                "post_code": "36732",
                "locality": "Demopolis",
                "lng": -87.84215265612795,
                "lat": 32.51568196266918,
                "id": 13188,
                "google_place_url": "https://maps.google.com/?q=Demopolis,+AL,+USA&ftid=0x888598167cb1f367:0xd1cd56a259858fdd",
                "google_place_id": "ChIJx9EZWxyYhYgR__YvPJIumwM",
                "formatted_address": "214 S Glover Ave, Demopolis, AL 36732, USA",
                "display_rule": "detect",
                "country_code": "US"
            }
        },
        {
            "wifi": {
                "id": 19
            },
            "theme": null,
            "template": null,
            "secure_access_only": false,
            "recs_only_name": "test",
            "recs_only_key": "ppxdwwf",
            "recs_only_image": "",
            "recs_only_enabled": true,
            "recommendations": [
                {
                    "key": "rwkknhc",
                    "id": 80
                }
            ],
            "parking": null,
            "name": "this guidebook name is updated",
            "key": "gcmtxmh",
            "is_template": false,
            "is_published": true,
            "informations": [
                {
                    "id": 138
                }
            ],
            "image": null,
            "id": 200762,
            "host_user_id": 201818,
            "host_intro": null,
            "guidebooks": null,
            "directions": null,
            "default_path": "",
            "checkout": null,
            "checkin": {
                "id": 39
            },
            "address": {
                "timezone": "Australia/Sydney",
                "street_number": "51",
                "street_2": "",
                "street": "Alexander St",
                "state": "NSW",
                "prefix": "",
                "post_code": "",
                "locality": "Crows Nest",
                "lng": 151.2021977,
                "lat": -33.8271108,
                "id": 346,
                "google_place_url": "",
                "google_place_id": null,
                "formatted_address": "",
                "display_rule": "detect",
                "country_code": "AU"
            }
        }
    ]
}
```

Fetch list of guidebooks for the user/agency

### HTTP Request

`GET https://v2apistaging.hostfully.com/openapi/v1/guidebooks/`

<aside class="notice">
Remember: You must replace <code>{{token}}</code> with your actual API Token.
</aside>

## GET /guidebooks/:uid

```shell
curl "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/200804"
  -H "Authorization: Bearer {{token}}"
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://v2apistaging.hostfully.com/openapi/v1/guidebooks/200804")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["authorization"] = 'Bearer {{token}}'

response = http.request(request)
puts response.read_body
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === this.DONE) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/200804");
xhr.setRequestHeader("authorization", "Bearer {{token}}");

xhr.send(data);
```

```python
import requests

url = "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/200804"

headers = {'authorization': 'Bearer {{token}}'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

> Make sure to replace `{{token}}` with your actual API Token.

> The above command returns JSON structured like this:

```json
{
    "data": {
        "wifi": {
            "id": 22
        },
        "theme": null,
        "template": null,
        "secure_access_only": false,
        "recs_only_name": "",
        "recs_only_key": "pvhqfkq",
        "recs_only_image": "",
        "recs_only_enabled": false,
        "recommendations": [
            {
                "website": "http://www.marengocountyhistoricalsociety.com/bluff-hall/",
                "phone_number": "+1 334-289-9644",
                "name": "Bluff Hall",
                "key": "rkxzqtw",
                "image": "https://cdn.filestackcontent.com/03F0pIaSh2DgG4QLiQRF",
                "id": 12878,
                "category": {
                    "user_id": 0,
                    "type": "recommendation",
                    "order": 3,
                    "name_txn": {
                        "zh-TW": "景點",
                        "pt-BR": "Atrações",
                        "pl-PL": "Atrakcje",
                        "ja-JP": "アトラクション",
                        "it-IT": "Attrazioni",
                        "fr-FR": "Attractions",
                        "es-ES": "Atracciones",
                        "de-DE": "Attraktionen"
                    },
                    "name": "attractions",
                    "is_default": true,
                    "id": 5,
                    "icon": "PhotoCamera",
                    "description_txn": {},
                    "description": "Attractions, Parks & Museums",
                    "color": "#03a9f4"
                },
                "batch_ref": null,
                "address": {
                    "timezone": "America/Chicago",
                    "street_number": "407",
                    "street_2": "",
                    "street": "N Commissioners Ave",
                    "state": "AL",
                    "prefix": "",
                    "post_code": "36732",
                    "locality": "Demopolis",
                    "lng": -87.8403467,
                    "lat": 32.5202275,
                    "id": 13189,
                    "google_place_url": "https://maps.google.com/?cid=4794307992065788176",
                    "google_place_id": "ChIJLY8R4fWXhYgREMnlqrfNiEI",
                    "formatted_address": "407 N Commissioners Ave, Demopolis, AL 36732, USA",
                    "display_rule": "detect",
                    "country_code": "US"
                }
            }
        ],
        "properties": [],
        "parking": {
            "id": 17
        },
        "name": "Demo Guidebook",
        "marketplace_items": null,
        "locales": [],
        "key": "gkhlmxc",
        "is_template": false,
        "is_published": true,
        "informations": [
            {
                "use_external_link": false,
                "title": "welcome to our home",
                "secure_access_only": false,
                "name": "demo house manual card",
                "image": "",
                "id": 157,
                "icon": "DirectionsCar",
                "external_link": "",
                "category": null
            }
        ],
        "image": "https://cdn.filestackcontent.com/FJk3KmqQ6yl4QUe5nJgB",
        "id": 200804,
        "host_user_id": 201818,
        "host_intro": {
            "id": 39
        },
        "guidebooks": [],
        "directions": {
            "id": 17
        },
        "default_path": "",
        "checkout": {
            "id": 29
        },
        "checkin": {
            "id": 46
        },
        "bookingsync_id": null,
        "batch_ref": null,
        "address": {
            "timezone": "America/Chicago",
            "street_number": "214",
            "street_2": "",
            "street": "S Glover Ave",
            "state": "AL",
            "prefix": "",
            "post_code": "36732",
            "locality": "Demopolis",
            "lng": -87.84215265612795,
            "lat": 32.51568196266918,
            "id": 13188,
            "google_place_url": "https://maps.google.com/?q=Demopolis,+AL,+USA&ftid=0x888598167cb1f367:0xd1cd56a259858fdd",
            "google_place_id": "ChIJx9EZWxyYhYgR__YvPJIumwM",
            "formatted_address": "214 S Glover Ave, Demopolis, AL 36732, USA",
            "display_rule": "detect",
            "country_code": "US"
        }
    }
}
```

Fetch simple guidebook info by id

### HTTP Request

`GET https://v2apistaging.hostfully.com/openapi/v1/guidebooks/:id`

### Path Parameters

Parameter | Type |  Description
--------- | ---- | -----------
:id | integer | The ID of the guidebook to retrieve

## GET /guidebooks/key/:key

```shell
curl "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/key/gkhlmxc"
  -H "Authorization: Bearer {{token}}"
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://v2apistaging.hostfully.com/openapi/v1/guidebooks/key/gkhlmxc")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["authorization"] = 'Bearer {{token}}'

response = http.request(request)
puts response.read_body
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === this.DONE) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/key/gkhlmxc");
xhr.setRequestHeader("authorization", "Bearer {{token}}");

xhr.send(data);
```

```python
import requests

url = "https://v2apistaging.hostfully.com/openapi/v1/guidebooks/key/gkhlmxc"

headers = {'authorization': 'Bearer {{token}}'}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

> Make sure to replace `{{token}}` with your actual API Token and `gkhlmxc` with the guidebook key.

> The above command returns JSON structured like this:

```json
{
    "data": {
        "wifi": {
            "wifi_provided": true,
            "wifi_password": "wifi-password",
            "network_name": "wifi-name",
            "label": "wifi demo",
            "id": 22,
            ...
        },
        "recommendations": [
            {
                "why_recommended": "Museum in Demopolis",
                "website": "http://www.marengocountyhistoricalsociety.com/bluff-hall/",
                "phone_number": "+1 334-289-9644",
                "name": "Bluff Hall",
                "image": "https://cdn.filestackcontent.com/03F0pIaSh2DgG4QLiQRF",
                "category": {
                    "name": "attractions",
                    "description": "Attractions, Parks & Museums",
                    "color": "#03a9f4"
                },
                "address": {
                    "street_number": "407",
                    "street": "N Commissioners Ave",
                    "state": "AL",
                    "post_code": "36732",
                    "locality": "Demopolis",
                    "lng": -87.8403467,
                    "lat": 32.5202275,
                    "google_place_id": "ChIJLY8R4fWXhYgREMnlqrfNiEI",
                    "formatted_address": "407 N Commissioners Ave, Demopolis, AL 36732, USA",
                    "country_code": "US"
                }
            }
        ],
        "parking": {
            "show_parking_details": false,
            "parking_text": "<p>Feel free to park in the driveway or on the street.  Please don't block any neighboring driveway.</p>",
            "on_street_available": true,
            "label": "demo parking",
            "expensive_nearby": false,
            "economical_available": false,
            "driveway_available": true
            ...
        },
        "name": "Demo Guidebook",
        "key": "gkhlmxc",
        "is_published": true,
        "informations": [
            {
                "title": "welcome to our home",
                "name": "demo house manual card",
                "image": "",
                "icon": "DirectionsCar",
                "content": "<p>welcome to our house!</p><p><br /></p><p>here are our basic rules:</p><p><br /></p><p>1) don't break things</p><p>2) no parties</p>",
                ...
            }
        ],
        "image": "https://cdn.filestackcontent.com/FJk3KmqQ6yl4QUe5nJgB",
        "id": 200804,
        "host_user_id": 201818,
        "host_intro": {
            "label": "demo host intro",
            "image": "https://cdn.filestackcontent.com/2iVq7D2bS6OFk3A5MgN4",
            "host_name": "frederick demonstrator",
            "host_intro": "<p>hi!   this is our welcome message</p>",
            "host_email": "demo@hostfully.com",
            ...
        },
        "directions": {
            "show_taxi": true,
            "additional_directions": "<p>this is how you get to the listing</p>",
            "taxi_text": "<p>to get here by taxi, give the driver our address.</p>",
            "label": "demo directions",
            ...
        },
        "checkout": {
            "towels_on_floor": false,
            "towels_in_tub": false,
            "take_out_trash": true,
            "store_bags_after_checkout": true,
            "sign_guestbook": false,
            "show_late_checkout": true,
            "rearrange_furniture": false,
            "lock_doors": false,
            "late_checkout_sometimes": true,
            "late_checkout_no": false,
            "late_checkout_contact": true,
            "label": "checkout demo",
            "key_lockbox": true,
            "key_inside": false,
            "electrical_off": true,
            "door_unlocked": true,
            "dishes_in_washer": false,
            "custom_fields": {},
            "clean_dishes": true,
            "checkout_time": "11:00 AM",
            "checkout_text": "<p>demo checkout information</p>",
            "beds_unmade": true
        },
        "checkin": {
            "self_access_meet": true,
            "self_access_lockbox": false,
            "self_access_keyless": false,
            "self_access_email": false,
            "self_access_codes": true,
            "label": "demo checkin",
            "early_checkin_text": "<p>custom checkin html</p><ul><li>list</li><li>item</li></ul>",
            "early_checkin_sometimes": true,
            "early_checkin_never": false,
            "early_checkin_alternative": false,
            "checkin_time": "2:00 PM",
            "checkin_text": "<p>custom access information</p>",
            "bag_storage_allowed": false,
            "access_image": null
        },
        "address": {
            "timezone": "America/Chicago",
            "street_number": "214",
            "street_2": "",
            "street": "S Glover Ave",
            "state": "AL",
            "prefix": "",
            "post_code": "36732",
            "locality": "Demopolis",
            "lng": -87.84215265612795,
            "lat": 32.51568196266918,
            "id": 13188,
            "google_place_url": "https://maps.google.com/?q=Demopolis,+AL,+USA&ftid=0x888598167cb1f367:0xd1cd56a259858fdd",
            "google_place_id": "ChIJx9EZWxyYhYgR__YvPJIumwM",
            "formatted_address": "214 S Glover Ave, Demopolis, AL 36732, USA",
            "display_rule": "detect",
            "country_code": "US"
        }
    }
}
```

Fetch simple guidebook info by id

### HTTP Request

`GET https://v2apistaging.hostfully.com/openapi/v1/guidebooks/key/:key`

### Path Parameters

Parameter | Type |  Description
--------- | ---- | -----------
:key | string | The key of the guidebook to retrieve



