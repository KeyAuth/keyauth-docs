---
description: How to send and retrieve chat messages
---

# Chat channels

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="chatget" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
chatget
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channel" type="string" %}
Name of chat channel to retrieve chat messages from
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" type="string" %}
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
{"success":true,"message":"Successfully retrieved chat messages","messages":[{"author":"3Y8FC2-MRHKUO-U9RH8I-GNHD2U-THK4X8-PW584D","message":"ok","timestamp":"1659290719"},{"author":"3Y8FC2-MRHKUO-U9RH8I-GNHD2U-THK4X8-PW584D","message":"ok","timestamp":"1659290719"}]}
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

type=chatget&name=test&ownerid=tiQhtH5R88&sessionid=hRrP2YKnix&channel=test
```

GET request example:

[https://keyauth.win/api/1.2/?type=chatget\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix\&channel=test](https://keyauth.win/api/1.2/?type=chatget\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix\&channel=test)

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="chatsend" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
chatsend
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channel" type="string" %}
Name of chat channel where you're sending chat messages
{% endswagger-parameter %}

{% swagger-parameter in="body" name="message" type="string" %}
Contents of chat message you're sending
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sessionid" type="string" %}
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

type=chatsend&name=test&ownerid=tiQhtH5R88&sessionid=hRrP2YKnix&channel=test&message=hello
```

GET request example:

[https://keyauth.win/api/1.2/?type=chatsend\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix\&channel=test\&message=hello](https://keyauth.win/api/1.2/?type=chatsend\&name=test\&ownerid=tiQhtH5R88\&sessionid=hRrP2YKnix\&channel=test\&message=hello)
