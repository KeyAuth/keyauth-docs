---
description: Use key to add subscription to user
---

# Upgrade

{% hint style="warning" %}
Do **not** log the user in after a successful upgrade, the upgrade endpoint is simply for a user to activate a key on their account. There's no password verification, so it would be unsafe for you to log the user in because all the user needs is an account username and valid key.
{% endhint %}

{% hint style="info" %}
Content-Type: application/x-www-form-urlencoded
{% endhint %}

{% swagger baseUrl="https://keyauth.win" path="/api/1.2/" method="post" summary="upgrade" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="type" type="string" %}
upgrade
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
user's username they want to upgrade	
{% endswagger-parameter %}

{% swagger-parameter in="body" name="key" type="string" %}
user's input for license key	
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
{"success":true,"message":"Upgraded successfully"}
```
{% endtab %}

{% tab title="Username Invalid" %}
```javascript
{"success":false,"message":"Username not found."}
```
{% endtab %}

{% tab title="Key Invalid" %}
```javascript
{"success":false,"message":"Key Not Found."}
```
{% endtab %}

{% tab title="Key Used" %}
```javascript
{"success":false,"message":"Key Already Used."}
```
{% endtab %}

{% tab title="No subscriptions" %}
```javascript
{"success":false,"message":"There is no subscription created for your key level. Contact appplicaton developer."}
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

type=upgrade&username=test&key=test&sessionid=sessionid&name=test&ownerid=j9Gj0FTemM
```

Post request full link:

[https://keyauth.win/api/1.2/?type=upgrade\&username=test\&key=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM](https://keyauth.win/api/1.2/?type=upgrade\&username=test\&key=test\&sessionid=sessionid\&name=test\&ownerid=j9Gj0FTemM)
