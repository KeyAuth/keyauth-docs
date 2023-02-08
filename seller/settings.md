---
description: Application settings
---

# Settings

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Retrieve settings" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
getsettings
{% endswagger-parameter %}

{% swagger-response status="200" description="Get Settings Success" %}
```javascript
{"success":true,"message":"Retrieved Settings Successfully","enabled":true,"hwid-lock":false,"version":"1.2","download":"https://example.com/newfile.exe","webhook":"https://discord.com/api/webhooks/845394562955739136/dRFkbhyFf4Sn7tfPZOQHbltYhlSf00mBW0QSP2ezNdMkPXi3ub0WdALMuholsshc2yjH","resellerstore":"https://shoppy.gg/@resellerstore","disabledmsg":"This application is disabled","usernametakenmsg":"Username Already Exists.","licenseinvalidmsg":"License not found.","keytakenmsg":"Key Already Used.","nosubmsg":"There is no subscription created for your key level. Contact appplicaton developer.","userinvalidmsg":"Username not found.","passinvalidmsg":"Username not found.","hwidmismatchmsg":"HWID Doesn't match. Ask for key reset.","noactivesubmsg":"HWID Doesn't match. Ask for key reset.","blackedmsg":"You've been blacklisted from our application","pausedmsg":"Your Key is paused and cannot be used at the moment.","expiredmsg":"Your Key is paused and cannot be used at the moment.","sellixsecret":"VZuk5CT04gsjqTh5Yowr62ZmuRzby08P","dayresellerproductid":"5fe8f5a21db5a","weekresellerproductid":"5fe8f5a21db5a","monthresellerproductid":"5fe8f5a21db5a","liferesellerproductid":"5fe8f5a21db5a"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=getsettings](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=getsettings)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Update settings" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
updatesettings
{% endswagger-parameter %}

{% swagger-parameter in="query" name="enabled" type="boolean" required="true" %}
true or false
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hwidcheck" type="boolean" required="true" %}
true or false
{% endswagger-parameter %}

{% swagger-parameter in="query" name="ver" type="number" required="true" %}
Version number
{% endswagger-parameter %}

{% swagger-parameter in="query" name="download" type="string" required="true" %}
URL to download new application if version updated.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="webhook" type="string" required="true" %}
Discord webbook URL to send notifications, such as all logs and license activation notices. 
{% endswagger-parameter %}

{% swagger-parameter in="query" name="resellerstore" type="string" required="true" %}
Shop link if you choose to sell just keys to Resellers, rather than key access.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="appdisabled" type="string" required="true" %}
Error message if application is disabled.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="usernametaken" type="string" required="true" %}
Error message if username is taken.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keynotfound" type="string" required="true" %}
Error message if license key not found.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keyused" type="string" required="true" %}
Error message if license key already used.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="nosublevel" type="string" required="true" %}
Error message if no subscription for license key level.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="usernamenotfound" type="string" required="true" %}
Error message if user not found.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="passmismatch" type="string" required="true" %}
Error message if password does not match.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hwidmismatch" type="string" required="true" %}
Error message if HWID does not match.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="noactivesubs" type="string" required="true" %}
Error message if user does not have any active subscriptions.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hwidblacked" type="string" required="true" %}
Error message if user's HWID is blacklisted.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keypaused" type="string" required="true" %}
Error message if key is currently paused.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="keyexpired" type="string" required="true" %}
Error message if license key has expired.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sellixsecret" type="string" required="true" %}
Sellix Webbook Secret if you intend to use Sellix with KeyAuth so resellers can have access to the license keys they purchase.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="dayproduct" type="string" required="true" %}
Sellix 24 hour key product-ID if you intend to use Sellix with KeyAuth so resellers can have access to the license keys they purchase.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="weekproduct" type="string" required="true" %}
Sellix 7 day key product-ID if you intend to use Sellix with KeyAuth so resellers can have access to the license keys they purchase.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="monthproduct" type="string" required="true" %}
Sellix 30 day key product-ID if you intend to use Sellix with KeyAuth so resellers can have access to the license keys they purchase.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="lifetimeproduct" type="string" required="true" %}
Lifetime key product-ID if you intend to use Sellix with KeyAuth so resellers can have access to the license keys they purchase.
{% endswagger-parameter %}

{% swagger-response status="200" description="Update Settings Success" %}
```javascript
{"success":true,"message":"Settings successfully Updated"}
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

Example URL: [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=updatesettings\&enabled=true\&hwidcheck=true\&ver=1.0\&download=text\&webhook=text\&resellerstore=text\&appdisabled=text\&usernametaken=text\&keynotfound=text\&keyused=text\&nosublevel=text\&usernamenotfound=text\&passmismatch=text\&hwidmismatch=text\&noactivesubs=text\&hwidblacked=text\&keypaused=text\&keyexpired=text\&sellixsecret=text\&dayproduct=text\&weekproduct=text\&monthproduct=text\&lifetimeproduct=text](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=updatesettings\&enabled=true\&hwidcheck=true\&ver=1.0\&download=text\&webhook=text\&resellerstore=text\&appdisabled=text\&usernametaken=text\&keynotfound=text\&keyused=text\&nosublevel=text\&usernamenotfound=text\&passmismatch=text\&hwidmismatch=text\&noactivesubs=text\&hwidblacked=text\&keypaused=text\&keyexpired=text\&sellixsecret=text\&dayproduct=text\&weekproduct=text\&monthproduct=text\&lifetimeproduct=text)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Reset Hash" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
resethash
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Reset hash successfully!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resethash](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=resethash)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Add Hash" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addhash
{% endswagger-parameter %}

{% swagger-parameter in="query" name="hash" type="string" required="true" %}
MD5 hash you want to add
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Reset hash successfully!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addhash\&hash=md5hashhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addhash\&hash=md5hashhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Pause app" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
pauseapp
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Subscription paused application"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=pauseapp](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=pauseapp)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Unpause app" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
unpauseapp
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Subscription unpaused application"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unpauseapp](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unpauseapp)
