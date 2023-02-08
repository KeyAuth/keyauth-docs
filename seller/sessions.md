---
description: Sessions are created when application is initialized
---

# Sessions

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Kill session" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
kill
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sessid" type="string" required="true" %}
Session ID to kill
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully killed session!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=kill\&sessid=oXuqIIhtz3](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=kill\&sessid=oXuqIIhtz3)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Kill all sessions" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
killall
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully killed all sessions!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=killall](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=killall)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="List all sessions" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
fetchallsessions
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved sessions","sessions":[{"id":"iMdaoCGXWr","credential":null,"expiry":"1649063974","validated":"0"}]}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallsessions](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallsessions)
