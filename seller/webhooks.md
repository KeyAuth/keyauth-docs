---
description: >-
  Webhooks are used to send request from client without revealing the link
  you're sending request to
---

# Webhooks

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Create webhook" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addwebhook
{% endswagger-parameter %}

{% swagger-parameter in="query" name="baseurl" type="string" required="true" %}
URL that's hidden on KeyAuth server
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ua" type="string" %}
User agent, optional. If not set, it will default to 

`KeyAuth`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="authed" type="integer" %}
Determines whether user needs to be logged in (1) or not (0)
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully added webhook!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addwebhook\&baseurl=https://example.com/\&ua=ExampleUserAgent\&authed=1](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addwebhook\&baseurl=https://example.com/\&ua=ExampleUserAgent\&authed=1)
