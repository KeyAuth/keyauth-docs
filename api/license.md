---
description: Login with license key
---

# License

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="license" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
license
{% endswagger-parameter %}

{% swagger-parameter in="body" name="key" type="string" %}
user's input for license key	
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hwid" type="string" %}
Hardware ID if you want to lock user to certain hardware
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" type="string" %}
SessionID returned from initialization request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Your Application Name	
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


{% endswagger-parameter %}

{% swagger-response status="200" description="Responses listed below." %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"Logged in!","info":{"username":"DE4GMREP-DBY341-TPFKUM","subscriptions":[{"subscription":"default","expiry":"1628601282"}],"ip":"206.189.205.251"}}
```
{% endtab %}

{% tab title="User Banned" %}
```javascript
{"success":false,"message":"The user is banned"}
```
{% endtab %}

{% tab title="Password Invalid" %}
```javascript
{"success":false,"message":"Password does not match."}
```
{% endtab %}

{% tab title="Subscription Expired" %}
```javascript
{"success":false,"message":"No active subscriptions found."}
```
{% endtab %}

{% tab title="Username Taken" %}
```javascript
{"success":false,"message":"Username Already Exists."}
```
{% endtab %}

{% tab title="Key Invalid" %}
```javascript
{"success":false,"message":"Key Not Found."}
```
{% endtab %}

{% tab title="Key Used" %}
```javascript
{"success":false,"message":"Key Already Used."}
```
{% endtab %}

{% tab title="Key Banned" %}
```javascript
{"success":false,"message":"Your license is banned."}
```
{% endtab %}

{% tab title="No subscriptions" %}
```javascript
{"success":false,"message":"There is no subscription created for your key level. Contact appplicaton developer."}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}
{% endswagger %}

POST request example:

```http
POST /api/1.2/ HTTP/1.1
Host: keyauth.win
Content-Type: application/x-www-form-urlencoded
Content-Length: 84

type=license&key=test&hwid=hwidhere&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

GET request example:

[https://keyauth.win/api/1.2/?type=license\&key=test\&hwid=hwidhere\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=license\&key=test\&hwid=hwidhere\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)
