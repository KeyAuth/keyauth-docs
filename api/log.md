---
description: Send information to Application Logs
---

# Log

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="log" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
log
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pcuser" type="string" %}
username of client's machine	
{% endswagger-parameter %}

{% swagger-parameter in="body" name="message" type="string" %}
log message	
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
Content-Length: 79

type=log&pcuser=test&message=messagehere&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

GET request example:

[https://keyauth.win/api/1.2/?type=log\&pcuser=test\&message=messagehere\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=log\&pcuser=test\&message=messagehere\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)

