---
description: >-
  Subscriptions are added to the user when a key is redeemed (via registration
  or upgrade)
---

# Subscriptions

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Create subscription" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addsub
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Subscription Name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="level" type="string" required="true" %}
Subscription Level
{% endswagger-parameter %}

{% swagger-response status="200" description="Subscription Added" %}
```javascript
{"success":true,"message":"Successfully created subscription!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addsub\&name=subnamehere\&level=1](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addsub\&name=subnamehere\&level=1)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete subscription" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delappsub
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Subscription name to delete
{% endswagger-parameter %}

{% swagger-response status="200" description="Subscription Deleted" %}
```javascript
{"success":true,"message":"Successfully deleted subscription!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delappsub\&name=subnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delappsub\&name=subnamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Fetch all subscriptions" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" %}
fetchallsubs
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved subscriptions","subs":[{"name":"default","level":"1"}]}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallsubs](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallsubs)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Edit subscription" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" %}
editsub
{% endswagger-parameter %}

{% swagger-parameter in="query" required="true" name="sub" %}
Subscription's name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="level" %}
new level you're changing subscription to
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Subscription successfully edited"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=editsub\&sub=subscriptionnamehere\&level=2](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=editsub\&sub=subscriptionnamehere\&level=2)
