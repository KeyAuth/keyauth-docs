---
description: Blacklist IP or HWID
---

# Blacklists

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Add blacklist" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
black
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ip" type="string" required="false" %}
IP address you'd like to blacklist. If left blank, the IP address the request came from will be blacklisted.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hwid" type="string" required="false" %}
HWID you'd like to blacklist. If left blank, none will be blacklisted.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Blacklist Addition Successful"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=black\&ip=1.1.1.1\&hwid=abc](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=black\&ip=1.1.1.1\&hwid=abc)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete blacklist" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delblack
{% endswagger-parameter %}

{% swagger-parameter in="query" name="data" type="string" required="false" %}
Blacklisted data here
{% endswagger-parameter %}

{% swagger-parameter in="query" name="blacktype" type="string" required="false" %}
Type of blacklist data being deleted, either 

`ip`

 or 

`hwid`
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted blacklist!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delblack\&data=1.1.1.1\&blacktype=ip](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delblack\&data=1.1.1.1\&blacktype=ip)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete all blacklists" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delblacks
{% endswagger-parameter %}

{% swagger-parameter in="query" name="data" type="string" required="false" %}
Blacklisted data here
{% endswagger-parameter %}

{% swagger-parameter in="query" name="blacktype" type="string" required="false" %}
Type of blacklist data being deleted, either 

`ip`

 or 

`hwid`
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted all blacklists!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delblacks](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delblacks)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Fetch all blacklists" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="String" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="String" required="true" %}
fetchallblacks
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved blacklists","subs":[{"hwid":null,"ip":"1.1.1.1","type":"ip"},{"hwid":null,"ip":"8.8.8.8","type":"ip"}]}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallblacks](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallblacks)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Add whitelist" %}
{% swagger-description %}
Whitelist IP address so that VPN check is bypassed for it.
{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addWhite
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ip" type="string" required="false" %}
IP address you'd like to blacklist. If left blank, the IP address the request came from will be blacklisted.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully added whitelist!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addWhite\&ip=102.129.152.70](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addWhite\&ip=102.129.152.70)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete whitelist" %}
{% swagger-description %}
Remove whitelist for IP address.
{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delWhite
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ip" type="string" required="false" %}
IP address you'd like to blacklist. If left blank, the IP address the request came from will be blacklisted.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted whitelist!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delWhite\&ip=102.129.152.70](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delWhite\&ip=102.129.152.70)
