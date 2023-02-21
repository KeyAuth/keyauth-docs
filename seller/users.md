---
description: SellerAPI endpoints for manging users (created when a license is used)
---

# Users

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Create user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" type="string" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" type="string" %}
adduser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" required="true" type="string" %}
Username you want to create
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sub" required="true" type="string" %}
Name of subscription user will be given upon creation
{% endswagger-parameter %}

{% swagger-parameter in="query" name="expiry" type="integer" required="true" %}
Number of days from now until user expires
{% endswagger-parameter %}

{% swagger-parameter in="query" name="pass" type="string" %}
Optional. If you don't set, password will be set when the user first logs in.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="User successfully created" %}
```javascript
{"success":true,"message":"Successfully created user!"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=adduser\&user=usernamehere\&sub=default\&expiry=1\&pass=passwordhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=adduser\&user=usernamehere\&sub=default\&expiry=1\&pass=passwordhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
deluser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
Username to delete.
{% endswagger-parameter %}

{% swagger-response status="200" description="User Successfully Deleted. " %}
```javascript
{"success":true,"message":"Successfully Deleted User"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Lacking seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}

{% swagger-response status="406" description="Username isn't valid" %}
```javascript
{"success":false,"message":"User Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=deluser\&user=usernamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=deluser\&user=usernamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete expired users" %}
{% swagger-description %}





{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delexpusers
{% endswagger-parameter %}

{% swagger-response status="200" description="Deletion Successful " %}
```javascript
{"success":true,"message":"Successfully deleted expired users!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions." %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delexpusers](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delexpusers)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Reset user's HWID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
resetuser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
The key you're attempting to reset.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"Successfully Reset User"}
```
{% endtab %}

{% tab title="User Invalid" %}
```javascript
{"success":false,"message":"User Not Found"}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="Seller Key couldn't be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resetuser\&user=usernamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resetuser\&user=usernamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Set user(s) variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="String" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" %}
setvar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" required="true" %}
User(s) you're assigning variable. It can be 

`all`

 
{% endswagger-parameter %}

{% swagger-parameter in="query" name="var" required="true" %}
Name of user variable you want to create or update
{% endswagger-parameter %}

{% swagger-parameter in="query" name="data" required="true" %}
Data of user variable you're updating or creating
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully set variable!"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=setvar\&user=usernamehere\&var=varnamehere\&data=vardatahere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=setvar\&user=usernamehere\&var=varnamehere\&data=vardatahere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Get user variable data" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="String" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="String" required="true" %}
getvar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="String" required="true" %}
User you're getting variable for
{% endswagger-parameter %}

{% swagger-parameter in="query" name="var" type="String" required="true" %}
User variable name
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved variable","response":"vardatahere"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=getvar\&user=usernamehere\&var=varnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=getvar\&user=usernamehere\&var=varnamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Delete all user variables with name" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="String" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="String" required="true" %}
massUserVarDelete
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="String" required="true" %}
Name of user variable to delete
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted user variables with that name!"}

```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=16b46041c1aaeb097e9fc1928c27a36d\&type=massUserVarDelete\&name=discord](https://keyauth.win/api/seller/?sellerkey=16b46041c1aaeb097e9fc1928c27a36d\&type=massUserVarDelete\&name=discord)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Ban user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
banuser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
Username to ban.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="reason" type="string" %}
Ban reason
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully banned user!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Lacking seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:**[ **** ](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=banuser\&user=usernamehere\&reason=banreasonhere)****[https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=banuser\&user=usernamehere\&reason=banreasonhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=banuser\&user=usernamehere\&reason=banreasonhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Unban user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
unbanuser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
Username to unban.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully unbanned user!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Lacking seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unbanuser\&user=usernamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unbanuser\&user=usernamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Delete user variable" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="String" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="String" required="true" %}
deluservar
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="String" required="true" %}
User you're deleting variable for
{% endswagger-parameter %}

{% swagger-parameter in="query" name="var" type="String" required="true" %}
User variable name
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted variable!"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=deluservar\&user=usernamehere\&var=varnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=deluservar\&user=usernamehere\&var=varnamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Delete user's subscription" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="String" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="String" required="true" %}
delsub
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="String" required="true" %}
User you're deleting subscription for
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sub" type="String" required="true" %}
Subscription name
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted subscription!"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delsub\&user=usernamehere\&sub=subnamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delsub\&user=usernamehere\&sub=subnamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Extend user(s)" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
extend
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
username to add subscription to, you can do 

`all`

 to extend all users
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sub" type="string" required="true" %}
name of subscription to add to user(s)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="expiry" type="integer" required="true" %}
duration of subscription, in days.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="activeOnly" type="integer" %}
Only extend users with active subscription that matches exact subscription you're extending. 

`1`

 for yes, 

`0`

 or don't include the parameter for no.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully extended user(s)!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=extend\&user=usernamehere\&sub=default\&expiry=1](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=extend\&user=usernamehere\&sub=default\&expiry=1)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Subtract from user subscription" %}
{% swagger-description %}
Remove time from a user's subscription. Time unit is in seconds.
{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
subtract
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
username to add subscription to, you can do 

`all`

 to extend all users
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sub" type="string" required="true" %}
name of subscription to add to user(s)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="seconds" type="integer" required="true" %}
amount of time to remove from user's subscription, in seconds
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully extended user(s)!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=subtract\&user=usernamehere\&sub=default\&seconds=3600](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=subtract\&user=usernamehere\&sub=default\&seconds=3600)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete all users" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delallusers
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully deleted all users!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delallusers](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delallusers)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Reset all user's HWID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
resetalluser
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully reset all users!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resetalluser](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resetalluser)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Verify user exists" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" %}
verifyuser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" required="true" %}
Username you want to check exists
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"User Successfully Verified"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=verifyuser\&user=usernamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=verifyuser\&user=usernamehere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Add HWID to user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addhwiduser
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
User you're adding HWID to
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hwid" type="string" required="true" %}
HWID you're adding to user.
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```
{"success":true,"message":"Added HWID"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addhwiduser\&user=usernamehere\&hwid=additionalhwidhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addhwiduser\&user=usernamehere\&hwid=additionalhwidhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Fetch all users" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
fetchallusers
{% endswagger-parameter %}

{% swagger-response status="200" description="Fetch user successful " %}
```javascript
{"success":true,"message":"Successfully Retrieved Users","users":[{"username":"4op2kbwfumal53rvk8ejljurepkup5n6","password":"$2y$10$LcjA0ML4FtNLLSeOqiyrau0JC0.LTfOYuVrHa6d19EGde05m63Mgi","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"M96zo49","password":"$2y$10$9tnHqlME8.Ej4kviYi6rVOlLoZNNJe4pZn.t6JjjtsA5Lp4pyoiSS","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"ZB8wdNX","password":"$2y$10$ptc5zUSyRn0LV30TdWxt9u..n8cKNFaxOpLZnxm2upt8CQygpTL2y","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"SNf70X5","password":"$2y$10$VsDb6ml/T1XdZ6sXWpInQ.iO45BgOh1WZ9odZspJi0ivv96/lcKz6","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"GShl5NG","password":"$2y$10$rwMywfQpud8kE39Edtdu0OVNE0R9yUWbIN.YxRFLF23173Ue3mSnK","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"jim","password":"$2y$10$HiYMHk8WXY2ciHYjYzn/EuFHgUfNzESatvzmbpTkU2tZJKPBK6Vii","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"bobson","password":"$2y$10$vWNr7jFGyveyD8SsXTc3benyYn.rGA4j9MXDfq2umFJKAO1S30qIy","expires":"","hwid":"server","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"FZ8G4ZMF-GYN5CW-IOW43R","password":"$2y$10$PXWpbVM/S8SiloLhYE2EV.9va3LkmwhUOGu07t/eaUv.q46sKkBUW","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"SEV9896C-7DUH8L-G5ETJC","password":"$2y$10$iXZh0BC9cusmlKW1M4dlG.0MIGPo3sMhOIrDE2mk27L6OdBgDfQ5C","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"mak","password":"$2y$10$Eboir6/msb/tvHty7.pAiejpFS//mn.0wgZj6eoCkblRe1RTmhYGS","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"03N5ZG-0UG1V8-C49UNP-L52ZGX-Y28XAO-43X10J","password":"$2y$10$0cMoUZdWsuDAXl905XkfBeliV/TcZb2iFnOhzzrLx3lCwtPkA8YQG","expires":"","hwid":"","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"DVHDD7-LQ3TG9-1YKM93-2X69MH-O053OX-QG5QJG","password":"$2y$10$pMC/2GQL6SUjFGz7Dhzr7.ewVNvluQpCn.rb3Ua6qLnyPy67HeEoO","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"},{"username":"ESSVS12W-S3A2Y9-YICUP6","password":"$2y$10$aQoNaHRLHSqkJgtyem64Y.4totqxnKxuYKX1yw8t9w0VlqEDvK0ki","expires":"","hwid":"S-1-5-21-213299988-1053324923-381067229-1001","app":"db40d586f4b189e04e5c18c3c94b7e72221be3f6551995adc05236948d1762bc","banned":null,"ip":"131.247.244.240"}]}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}

{% swagger-response status="406" description="Application doesn't contain any users." %}
```javascript
{"success":false,"message":"No Users Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallusers](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallusers)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Change password" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" required="true" %}
resetpw
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" required="true" %}
User you're resetting password for
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Password reset successful"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resetpw\&user=usernamehere\&passwd=passwordhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resetpw\&user=usernamehere\&passwd=passwordhere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Fetch all user variables" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="true" name="type" %}
fetchalluservars
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully retrieved user variables","vars":[{"name":"varnamehere","data":"vardatahere","user":"mak"}]}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchalluservars](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchalluservars)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Retrieve user data" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="true" name="type" %}
userdata
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="" required="true" %}
user to retrieve user data on
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"username":"mak","subscriptions":[{"subscription":"default","expiry":"1642968815","timeleft":2588179},{"subscription":"default","expiry":"1671913200","timeleft":31532564},{"subscription":"default","expiry":"1671915000","timeleft":31534364}],"ip":"8.8.8.8","hwid":"asassa","createdate":"1640379353","lastlogin":"1640373896"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=userdata\&user=usernamehere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=userdata\&user=usernamehere)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Fetch all usernames" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="true" name="type" %}
fetchallusernames
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Successfully Retrieved Usernames","usernames":["makAndCheese","0BGXUZ-H13UTN-LKMNWV-U5ECW1-W7RLZF-6NZAJW"]}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallusernames](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallusernames)

{% swagger method="get" path="/api/seller" baseUrl="https://keyauth.win" summary="Count subscriptions" %}
{% swagger-description %}
Count subscriptions under a subscription name. Only returns count of active, non-expired subscriptions.
{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" required="true" type="string" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="true" name="type" type="string" %}
countsubs
{% endswagger-parameter %}

{% swagger-parameter in="query" name="name" type="string" %}
Subscription name you're trying to count subscriptions of.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{"success":true,"message":"Subscription count found successfully","count":"29"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=countsubs\&name=default](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=countsubs\&name=default)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Set user's cooldown" %}
{% swagger-description %}
Set cooldown for user to reset HWID
{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
setcooldown
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
User you're adding HWID to
{% endswagger-parameter %}

{% swagger-parameter in="query" name="cooldown" type="string" required="true" %}
Cooldown time, in seconds
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```json
{"success":true,"message":"Cooldown set successfully!"}
```
{% endswagger-response %}

{% swagger-response status="403" description="Missing seller permissions" %}
```javascript
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=setcooldown\&user=usernamehere\&cooldown=3600](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=setcooldown\&user=usernamehere\&cooldown=3600)
