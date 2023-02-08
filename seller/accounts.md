---
description: Create and delete Manager & Reseller accounts
---

# Accounts

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Create account" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addAccount
{% endswagger-parameter %}

{% swagger-parameter in="query" name="role" required="true" type="string" %}
Account role. Either 

`Manager`

 or 

`Reseller`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="pass" type="string" required="true" %}
Account password
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keylevels" type="string" %}
(optional) allowed key levels for Reseller account. make sure you comma delimit, e.g. 

`1,4,8`
{% endswagger-parameter %}

{% swagger-parameter in="query" name="email" required="true" type="string" %}
Account email
{% endswagger-parameter %}

{% swagger-parameter in="query" name="perms" type="string" %}
Only applicable when creating accounts with 

`Manager`

 role. Controls what pages account can see. If not specified, all pages can be seen. You can get the number you want by going to 

[https://keyauth.cc/app/?page=manage-accs](https://keyauth.cc/app/?page=manage-accs)

, pressing "Create Account" button and then selecting "Manager" as account role. When you change the permissions at the bottom of the modal, you'll see the number for the value change.
{% endswagger-parameter %}

{% swagger-response status="200" description="Get Settings Success" %}
```javascript
{"success":true,"message":"Successfully created account!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Application with specified seller key doesn't exist" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addAccount\&role=Manager\&user=managerTest\&pass=9e2teHRMStxWUVoa7Haqriz6Y\&keylevels=1,2,3\&email=managerTest@gmail.com](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addAccount\&role=Manager\&user=managerTest\&pass=9e2teHRMStxWUVoa7Haqriz6Y\&keylevels=1,2,3\&email=managerTest@gmail.com)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete account" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
deleteAccount
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
Account username of account to delete
{% endswagger-parameter %}

{% swagger-response status="200" description="Delete account success" %}
```javascript
{"success":true,"message":"Successfully deleted account!"}
```
{% endswagger-response %}
{% endswagger %}

Example URL: [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=deleteAccount\&user=managerTest](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=deleteAccount\&user=managerTest)
