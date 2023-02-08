---
description: Check if HWID or IP address blacklisted
---

# Check blacklist

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="checkblacklist" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
checkblacklist
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hwid" type="string" %}
(optional) HWID to check if in blacklist.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Application Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" type="string" %}
Session ID obtained from Initialization request
{% endswagger-parameter %}

{% swagger-response status="200" description="Responses Listed Below." %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"Webhook response"}
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
Content-Length: 83

type=checkblacklist&name=test&ownerid=tiQhtH5R88&sessionid=hRrP2YKnix&hwid=hwidhere
```

GET request example:

[https://keyauth.win/api/1.2/?type=checkblacklist\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix\&hwid=hwidhere](https://keyauth.win/api/1.2/?type=checkblacklist\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix\&hwid=hwidhere)
