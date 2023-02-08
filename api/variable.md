---
description: Grab Server Sided Variables
---

# Variable

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" required="true" %}
var
{% endswagger-parameter %}

{% swagger-parameter in="body" name="varid" type="string" required="true" %}
Variable Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Application Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" required="true" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" type="string" required="true" %}
SessionID retrieved from initialization request
{% endswagger-parameter %}

{% swagger-response status="200" description="Responses Listed Below." %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"hello from variable"}
```
{% endtab %}

{% tab title="Invalid Session" %}
```javascript
{"success":false,"message":"Session is not validated."}
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
Content-Length: 79

type=var&varid=test&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

GET request example:

[https://keyauth.win/api/1.2/?type=var\&varid=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=var\&varid=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)
