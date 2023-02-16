---
description: >-
  SellerAPI endpoints for manging licenses (keys given to your customers to
  register users)
---

# Licenses

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Create license(s)" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
add
{% endswagger-parameter %}

{% swagger-parameter in="query" name="format" type="string" %}
You may set to 

`text`

 if you don't want in JSON. If not set, will default to JSON.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="expiry" type="integer" required="true" %}
How Long License will last, in days.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="mask" type="string" %}
If not set, defaults to "XXXXXX-XXXXXX-XXXXXX-XXXXXX-XXXXXX-XXXXXX"
{% endswagger-parameter %}

{% swagger-parameter in="query" name="level" type="integer" %}
If not set, defaults to 1.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="amount" type="integer" %}
If not set, defaults to 1.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="owner" type="string" %}
Optional. Can set to the username of one of your resellers. if not set, defaults to 

`SellerAPI`
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns Single License" %}
```javascript
{"success":true,"message":"Key Successfully Generated","key":"AVZKQ7-TXPIPH-3L6GZS-J0M6EW-Q7NMR7-DASOAL"}
```
{% endswagger-response %}

{% swagger-response status="302" description="Returns Multiple Licenses" %}
```javascript
{"success":true,"message":"Keys Successfully Generated","keys":["CDOH16-UW234U-LKPCO0-T5ZDKI-RMD289-3MHU65","F7U7PX-QTXFC2-F419BX-6YYIRV-4U8OK3-KHJWOL"]}
```
{% endswagger-response %}

{% swagger-response status="403" description="Amount too high" %}
```javascript
{"success":false,"message":"You can't generate more than 50 keys"}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```javascript
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}

{% swagger-response status="406" description="Expiry Not Defined" %}
```javascript
{"success":false,"message":"Expiry Not Set"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=add\&expiry=1\&mask=XXXXXX-XXXXXX-XXXXXX-XXXXXX-XXXXXX-XXXXXX\&level=1\&amount=1\&format=json](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=add\&expiry=1\&mask=XXXXXX-XXXXXX-XXXXXX-XXXXXX-XXXXXX-XXXXXX\&level=1\&amount=1\&format=json)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Verify license exists" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
verify
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="boolean" required="true" %}
License key
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Key Successfully Verified"}
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

{% swagger-response status="406" description="Key Invalid" %}
```javascript
{"success":false,"message":"Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=verify\&key=keyhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=verify\&key=keyhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Use license to create user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
activate
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" type="string" required="true" %}
username you would like to create
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" required="true" %}
valid key you're activating
{% endswagger-parameter %}

{% swagger-parameter in="query" name="pass" type="string" required="true" %}
password for account being made
{% endswagger-parameter %}

{% swagger-response status="200" description="Success? Maybe." %}
{% tabs %}
{% tab title="Success" %}
```javascript
{"success":true,"message":"Logged in!","info":{"username":"DE4GMREP-DBY341-TPFKUM","subscriptions":[{"subscription":"default","expiry":"1628601282"}],"ip":"206.189.205.251"}}
```
{% endtab %}

{% tab title="Username Taken" %}
```javascript
{"success":false,"message":"Username Already Exists."}
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

{% tab title="Key Banned" %}
```javascript
{"success":false,"message":"Your license is banned."}
```
{% endtab %}

{% tab title="HWID Blacklisted" %}
```javascript
{"success":false,"message":"HWID is blacklisted"}
```
{% endtab %}

{% tab title="No subscriptions" %}
```javascript
{"success":false,"message":"No active subscriptions found."}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=activate\&user=usernamehere\&key=keyhere\&pass=passwordhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=activate\&user=usernamehere\&key=keyhere\&pass=passwordhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete license" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
del
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" required="true" %}
The key you're attempting to delete.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="userToo" type="string" %}
(optional) delete user also. 

`1`

 for yes, 

`0`

 or leave blank for no.
{% endswagger-parameter %}

{% swagger-response status="200" description="Key Deletion Successful " %}
```javascript
{"success":true,"message":"Successfully Deleted License"}
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

{% swagger-response status="406" description="Key Invalid" %}
```javascript
{"success":false,"message":"Key Not Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=del\&key=15ME7B-7MCRNI-DUMWAS-3KQ3F6-1URVQI-Z8WQHZ\&userToo=0](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=del\&key=15ME7B-7MCRNI-DUMWAS-3KQ3F6-1URVQI-Z8WQHZ\&userToo=0)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete unused licenses" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delunused
{% endswagger-parameter %}

{% swagger-response status="200" description="Deletion Successful" %}
```javascript
{"success":true,"message":"Successfully Deleted Unused Licenses"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delunused](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delunused)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete used licenses" %}
{% swagger-description %}



{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delused
{% endswagger-parameter %}

{% swagger-response status="200" description="Deletion Successful" %}
```javascript
{"success":true,"message":"Deleted All Used Keys!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delused](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delused)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Delete all licenses" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
delalllicenses
{% endswagger-parameter %}

{% swagger-response status="200" description="All Licenses Deleted" %}
```javascript
{"success":true,"message":"Successfully Deleted All Licenses"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delalllicenses](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=delalllicenses)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Fetch all licenses" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="format" type="string" required="false" %}
You may set to 

`text`

 if you want just a list of keys, rather than all the info about the keys delivered via JSON.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
fetchallkeys
{% endswagger-parameter %}

{% swagger-response status="200" description="All Licenses Returned" %}
```javascript
{"success":true,"message":"Successfully Retrieved Licenses","keys":[{"key":"ZJ5C50-X3RHHF-06QTO8-TIT7VC-E12YSQ-XJ1G7G","note":"","expires":"7464960000","lastlogin":"","hwid":"","status":"Not Used","level":"1","genby":"SellerAPI","gendate":"1621361205","app":"22e10f0fd3602f6e4d49e490f166002f46ff667f99c1865243e662bb1eeefe88","cooldown":"","banned":"","ip":""},{"key":"ZED7IY-1GFBCW-SJDH5T-8X0Q5X-DUBCH4-CUAWLH","note":"","expires":"7464960000","lastlogin":"","hwid":"","status":"Not Used","level":"1","genby":"SellerAPI","gendate":"1621361213","app":"22e10f0fd3602f6e4d49e490f166002f46ff667f99c1865243e662bb1eeefe88","cooldown":"","banned":"","ip":""}]}
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

{% swagger-response status="406" description="No Keys Found" %}
```javascript
{"success":false,"message":"No License Keys Found"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallkeys](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=fetchallkeys)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Add time to unused licenses" %}
{% swagger-description %}
Note: if you want to add time to used licenses, you need to use extend users.
{% endswagger-description %}

{% swagger-parameter in="query" name="format" type="string" required="false" %}
You may set to 

`text`

 if you want just a list of keys, rather than all the info about the keys delivered via JSON.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
addtime
{% endswagger-parameter %}

{% swagger-parameter in="query" name="time" type="string" required="true" %}
Number of days you want to add to all unused licenses
{% endswagger-parameter %}

{% swagger-response status="200" description="Time added succesfully" %}
```json
{"success":true,"message":"Added time to unused licenses!"}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Missing seller permissions" %}
```json
{"success":false,"message":"Not authorized to use SellerAPI, please upgrade."}
```
{% endswagger-response %}

{% swagger-response status="404" description="No application with specified Seller Key could be found" %}
```json
{"success":false,"message":"Seller Key Not Found"}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Failed to add time" %}
```json
{"success":false,"message":"Failed to add time!"}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Unhandled Error" %}
```javascript
{"success":false,"message":"Unhandled Error! Contact us if you need help"}
```
{% endswagger-response %}
{% endswagger %}

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addtime\&time=1](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=addtime\&time=1)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Ban license" %}
{% swagger-description %}
Note: if you want to ban used license, you need to ban user.
{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
ban
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" required="true" %}
License key to ban
{% endswagger-parameter %}

{% swagger-parameter in="query" name="reason" type="string" required="true" %}
Ban reason
{% endswagger-parameter %}

{% swagger-parameter in="query" name="userToo" type="string" %}
(optional) ban user also. 

`1`

 for yes, 

`0`

 or leave blank for no.
{% endswagger-parameter %}

{% swagger-response status="200" description="Ban Successful" %}
```javascript
{"success":true,"message":"Successfully banned license!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=ban\&key=3PTO0V-TY0UET-1CTBZK-7BMTJX-DMX7B8-9R5712\&reason=reasonhere\&userToo=0](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=ban\&key=3PTO0V-TY0UET-1CTBZK-7BMTJX-DMX7B8-9R5712\&reason=reasonhere\&userToo=0)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Unban license" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
unban
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" type="string" required="true" %}
License key to unban
{% endswagger-parameter %}

{% swagger-response status="200" description="Unban Successful" %}
```javascript
{"success":true,"message":"Successfully unbanned license!"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unban\&key=keyhere](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=unban\&key=keyhere)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Retrieve license from user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
getkey
{% endswagger-parameter %}

{% swagger-parameter in="query" name="user" required="true" %}
User you're trying to find license from
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"key":"TEST-Z5TP4M-I1P3ZS-DVY1N1-1WDJDR-3NTI7E"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=getkey\&user=TEST-Z5TP4M-I1P3ZS-DVY1N1-1WDJDR-3NTI7E](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=getkey\&user=TEST-Z5TP4M-I1P3ZS-DVY1N1-1WDJDR-3NTI7E)

{% swagger baseUrl="https://keyauth.win" path="/api/seller" method="get" summary="Set note" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="sellerkey" type="string" required="true" %}
Found at 

[https://keyauth.cc/app/?page=seller-settings](https://keyauth.cc/app/?page=seller-settings)

, used to authenticate request and determine which application in use.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="type" type="string" required="true" %}
setnote
{% endswagger-parameter %}

{% swagger-parameter in="query" name="key" required="true" type="string" %}
License key you're going to set note for
{% endswagger-parameter %}

{% swagger-parameter in="query" name="note" type="string" required="true" %}
Note contents
{% endswagger-parameter %}

{% swagger-response status="200" description="Success" %}
```javascript
{"success":true,"message":"Successfully set note"}
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

**Example URL:** [https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=setnote\&key=TEST-Z5TP4M-I1P3ZS-DVY1N1-1WDJDR-3NTI7E\&note=this is my note](https://keyauth.win/api/seller/?sellerkey=sellerkeyhere\&type=setnote\&key=TEST-Z5TP4M-I1P3ZS-DVY1N1-1WDJDR-3NTI7E\&note=this%20is%20my%20note)
