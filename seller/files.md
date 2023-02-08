---
description: Files are used to download file in a more secure manner via KeyAuth
---

# Files

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Upload file" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
upload
{% endswagger-parameter %}

{% swagger-parameter in="query" name="url" type="string" required="true" %}
URL file is at. make sure it ends in the file extension or it won't work
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully added file!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=upload\&url=https://example.com/file.exe](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=upload\&url=https://example.com/file.exe)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete file" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delfile
{% endswagger-parameter %}

{% swagger-parameter in="query" name="fileid" type="string" required="true" %}
File ID to delete
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully added file!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delfile\&fileid=577167](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delfile\&fileid=577167)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete all files" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delallfiles
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted all files!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delallfiles](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delallfiles)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Fetch all files" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tyoe" required="true" %}
fetchallfiles
{% endswagger-parameter %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallfiles](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallfiles)
