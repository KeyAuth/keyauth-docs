---
description: In-app chat
---

# Chats

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Create channel" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addchannel
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Channel name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="delay" type="string" required="true" %}
Channel delay (in seconds)
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully created channel!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addchannel\&name=channelnamehere\&delay=1](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addchannel\&name=channelnamehere\&delay=1)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete channel" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delchannel
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Channel name
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted channel!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delchannel\&name=channelnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delchannel\&name=channelnamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Edit channel" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
editchan
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Channel name
{% endswagger-parameter %}

{% swagger-parameter in="query" name="delay" type="string" %}
delay in minutes that a user must wait before sending another message. decimals are allowed.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted channel!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=editchan\&name=testing\&delay=2](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=editchan\&name=testing\&delay=2)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Clear channel messages" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
clearchannel
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" required="true" %}
Channel name
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully cleared channel!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=clearchannel\&name=channelnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=clearchannel\&name=channelnamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Mute user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
muteuser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
User to mute
{% endswagger-parameter %}

{% swagger-parameter in="query" name="time" type="string" required="true" %}
Time to mute for (in seconds)
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully muted user!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=muteuser\&user=usernamehere\&time=60](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=muteuser\&user=usernamehere\&time=60)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Unmute user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
unmuteuser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
User to unmute
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully muted user!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unmuteuser\&user=usernamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unmuteuser\&user=usernamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Fetch all channels" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
fetchallchats
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved chats","chats":[{"name":"testing","delay":"19"}]}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallchats](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallchats)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Fetch all mutes" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
fetchallmutes
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved mutes","mutes":[{"user":"mak","time":"1649043282"}]}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=fetchallmutes\&type=fetchallmutes](https://keyauth.win/api/seller/?sellerkey=fetchallmutes\&type=fetchallmutes)
