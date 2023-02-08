---
description: Checking app is enabled, app has not been modified, etc.
---

# Initialization

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="init" %}
{% swagger-description %}
Ensure application is enabled, and the status of other settings, and return session ID.
{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" required="true" %}
init
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ver" type="string" required="true" %}
Application version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Application Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" required="true" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="enckey" type="string" %}
(optional) random GUID, increases security of request made to API. Read more at 

[Security Practices](../security-practices.md)


{% endswagger-parameter %}

{% swagger-response status="200" description="Responses Listed Below" %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"Initialized","sessionid":"cLylw99O4l"}
```
{% endtab %}

{% tab title="App Disabled" %}
```javascript
{"success":false,"message":"This application is disabled"}
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
Content-Length: 46

type=init&ver=1.0&name=test&ownerid=j9Gj0FTemM
```

GET request example:

[https://keyauth.win/api/1.2/?type=init\&ver=1.0\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=init\&ver=1.0\&name=test\&ownerid=j9Gj0FTemM)
