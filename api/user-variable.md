---
description: Set and retrieve variables specific to the user
---

# User Variable

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="setvar" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
setvar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="var" type="string" %}
User variable name you want to update data for
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data" type="string" %}
User variable data you're setting
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" %}
SessionID returned from initialization request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Application name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


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

type=setvar&var=test&data=test&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

GET request example:

[https://keyauth.win/api/1.2/?type=setvar\&var=test\&data=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=setvar\&var=test\&data=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="getvar" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
getvar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="var" type="string" %}
User variable name you want to get data for
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" %}
SessionID returned from initialization request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Application name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ownerid" type="string" %}
Your account OwnerID, find here: 

[https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)


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

type=getvar&var=test&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

GET request example:

[https://keyauth.win/api/1.2/?type=getvar\&var=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=getvar\&var=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)
