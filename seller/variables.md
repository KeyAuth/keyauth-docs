---
description: Variables are strings that can be stored server-side for increased security
---

# Variables

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Create variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addvar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Desired Variable Name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="data" type="string" required="true" %}
Data Associated with variable
{% endswagger-parameter %}

{% swagger-parameter in="query" name="authed" type="integer" required="true" %}
Determines whether user needs to be logged in (1) or not (0)
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully created variable!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Seller Key Not Found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addvar\&name=varnamehere\&data=vardatahere\&authed=1](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addvar\&name=varnamehere\&data=vardatahere\&authed=1)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Edit variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
editvar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="varid" type="string" required="true" %}
Variable name to edit
{% endswagger-parameter %}

{% swagger-parameter in="query" name="data" type="string" required="true" %}
Variable data to change
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully created variable!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Seller Key Not Found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=editvar\&varid=varnamehere\&data=vardatahere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=editvar\&varid=varnamehere\&data=vardatahere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Retrieve variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
retrvvar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Variable name to retrieve
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"vardatahere"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Seller Key Not Found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=retrvvar\&name=varnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=retrvvar\&name=varnamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Fetch all variables" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" %}
fetchallvars
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved variables","vars":[{"varid":"varnamehere","msg":"vardatahere"},{"varid":"varnamehere1","msg":"vardatahere1"}]}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallvars](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallvars)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delvar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Variable name to delete
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"vardatahere"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Seller Key Not Found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [ https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delvar\&name=varnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delvar\&name=varnamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete all variables" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delallvars
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted all variables!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delallvars](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delallvars)
