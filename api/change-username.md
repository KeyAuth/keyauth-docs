---
description: Allow users to change their usernames
---

# Change Username

{% hint style="warning" %}
User must be logged in (session has to be validated) to change username
{% endhint %}

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="changeUsername" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
changeUsername
{% endswagger-parameter %}

{% swagger-parameter in="body" name="newUsername" type="string" %}
New user that user desires
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

{% swagger-response status="200" description="Successfully changed username" %}
```json
{"success":true,"message":"Successfully changed username, user logged out."}
```
{% endswagger-response %}
{% endswagger %}

GET request example:

{% embed url="https://keyauth.win/api/1.2/?type=changeUsername&newUsername=makNewUser&sessionid=AvrnXhE19Q&name=example&ownerid=JjPMBVlIOd" %}

{% hint style="warning" %}
If successfull username change, the session is made invalid and the user will need to login with their username if they want to send anymore requests to KeyAuth
{% endhint %}
