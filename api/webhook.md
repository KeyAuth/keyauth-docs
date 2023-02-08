---
description: Send request securely from KeyAuth server
---

# Webhook

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="webhook" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
webhook
{% endswagger-parameter %}

{% swagger-parameter in="body" name="webid" type="string" %}
ID of the webhook created here 

[https://keyauth.cc/app/?page=webhooks](https://keyauth.cc/app/?page=webhooks)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="params" type="string" %}
Parameters that will be appended to base link of webhook. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="conttype" type="string" %}
(optional) Content type for the request. eg. 

`application/json`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" type="string" %}
SessionID returned from initialization request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Application Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


{% endswagger-parameter %}

{% swagger-response status="200" description="No response" %}
```
No response
```
{% endswagger-response %}
{% endswagger %}

POST request example:

```http
POST /api/1.2/ HTTP/1.1
Host: keyauth.win
Content-Type: application/x-www-form-urlencoded
Content-Length: 114

type=webhook&name=test&ownerid=tiQhtH5R88&sessionid=LxVe6GNLJu&webid=Sh1j25S5iX&params=?ok%3Dyes%26no%3Dok
```

GET request example:

[https://keyauth.win/api/1.2/?type=webhook\&name=test\&ownerid=tiQhtH5R88\&sessionid=LxVe6GNLJu\&webid=Sh1j25S5iX\&params=?ok=yes%26no=ok](https://keyauth.win/api/1.2/?type=webhook\&name=test\&ownerid=tiQhtH5R88\&sessionid=LxVe6GNLJu\&webid=Sh1j25S5iX\&params=?ok=yes%26no=ok)

