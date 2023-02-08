---
description: Check if session is validated (user signed in)
---

# Check session

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="check" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
check
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

{% swagger-response status="200" description="Session is validated" %}
```json
{"success":true,"message":"Session is validated."}
```
{% endswagger-response %}
{% endswagger %}

POST request example:

```http
POST /api/1.2/ HTTP/1.1
Host: keyauth.win
Content-Type: application/x-www-form-urlencoded
Content-Length: 60

type=check&name=test&ownerid=tiQhtH5R88&sessionid=LxVe6GNLJu
```

GET request example:

[https://keyauth.win/api/1.2/?type=check\&name=test\&ownerid=tiQhtH5R88\&sessionid=LxVe6GNLJu](https://keyauth.win/api/1.2/?type=check\&name=test\&ownerid=tiQhtH5R88\&sessionid=LxVe6GNLJu)
