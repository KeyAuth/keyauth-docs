---
description: Buttons for web loader
---

# Web Loader Buttons

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Retrieve all buttons" %}
{% swagger-description %}



{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
fetchallbuttons
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved buttons","buttons":[{"text":"Testing","value":"yes"}]}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Application with specified seller key doesn't exist" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallbuttons](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallbuttons)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Add button" %}
{% swagger-description %}



{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addbutton
{% endswagger-parameter %}

{% swagger-parameter in="query" name="value" type="string" %}
Desired button for the value (don't use spaces)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="text" type="string" %}
Desired text shown on button. Use spaces if you want to.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved buttons","buttons":[{"text":"Testing","value":"yes"}]}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Application with specified seller key doesn't exist" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addbutton\&value=test\&text=Testing Text](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addbutton\&value=test\&text=Testing%20Text)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete button" %}
{% swagger-description %}



{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delbutton
{% endswagger-parameter %}

{% swagger-parameter in="query" name="value" type="string" %}
Value of button you want to delete
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved buttons","buttons":[{"text":"Testing","value":"yes"}]}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Application with specified seller key doesn't exist" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delbutton\&value=test](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delbutton\&value=test)
