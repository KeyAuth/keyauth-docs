---
description: Fetch array of online users
---

# Fetch online users

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="fetchOnline" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
fetchOnline
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
{"success":true,"message":"Successfully fetched online users.","users":{"0":"NMAQCS-EY8HUI-23RRCE-596QCS-BA11SY-LBKBD2","credential":"NMAQCS-EY8HUI-23RRCE-596QCS-BA11SY-LBKBD2"}}
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

type=fetchOnline&name=test&ownerid=tiQhtH5R88&sessionid=hRrP2YKnix
```

GET request example:

[https://keyauth.win/api/1.2/?type=fetchOnline\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix](https://keyauth.win/api/1.2/?type=fetchOnline\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix)
