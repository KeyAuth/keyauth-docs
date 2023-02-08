---
description: Login with username & password
---

# Login

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="login" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" required="true" %}
login
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
user's input for username	
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pass" type="string" %}
user's input for password	
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

{% swagger-response status="200" description="Responses Listed Below" %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"Logged in!","info":{"username":"testing20","subscriptions":[{"subscription":"default","expiry":"1628514302"}],"ip":"206.189.205.251"}}
```
{% endtab %}

{% tab title="Username Invalid" %}
```javascript
{"success":false,"message":"Username not found."}
```
{% endtab %}

{% tab title="Password Invalid" %}
```javascript
{"success":false,"message":"Password does not match."}
```
{% endtab %}

{% tab title="User Banned" %}
```javascript
{"success":false,"message":"The user is banned"}
```
{% endtab %}

{% tab title="Subscription Expired" %}
```javascript
{"success":false,"message":"No active subscriptions found."}
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
Content-Length: 97

type=login&username=test&pass=test&hwid=hwidhere&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

&#x20;GET request example:

[https://keyauth.win/api/1.2/?type=login\&username=test\&pass=test\&hwid=hwidhere\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=login\&username=test\&pass=test\&hwid=hwidhere\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)
