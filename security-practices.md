---
description: Tips for security
---

# Security practices

KeyAuth is an authentication API, not a client-side obfuscation service.

So, when you see skids saying that KeyAuth is is "shit" because an unobfuscated program can be patched, pay them no attention.

KeyAuth along with authentication APIs that cost tens of thousands more provide no client-side obfuscation, so this is industry standard.&#x20;



The application developer (you) bear the reponsibility of adding obfuscation and checksums to stop memory patches to your program. However, KeyAuth does ensure that your program can't be bypassed with HTTP debugger or any other network modification tools, unlike auth.gg[ https://keyauth.cc/bypass/](https://keyauth.cc/bypass/)

{% hint style="warning" %}
There's no point in doing below steps if you're sending request from a server. As servers won't need this protection as the user won't be able to modify network traffic between the server and KeyAuth API
{% endhint %}

You're going to want to include a random GUID in the `enckey` paramater with the initialization request to the 1.2 API endpoint. Make sure the length of the GUID is 36 characters or less. You will send this GUID in the `enckey` parameter only on init, none of the other requests.

And then store this GUID along with your application secret for later checking. Like this `[GUID]-[secret]`

So if my GUID I passed in the `enckey` parameter was `4a59f8ca-b304-47` and my app secret is `76489f2ba92ddf9132e28d56870004a62d30ec5b40eaf2071ae48036e7144b5f` I want to store the string `4a59f8ca-b304-47-76489f2ba92ddf9132e28d56870004a62d30ec5b40eaf2071ae48036e7144b5f` for later use



**For initialization response:**

For init request responses, there's a signature header which is a SHA256 HMAC of the JSON response encoded with the application secret.

So the header is `signature: 8d0a11b00f44bee4e563117db28533943f5170854f5f65e69470c59bffb7d0d5` and the JSON response is:

```json
{"success":true,"message":"Initialized","sessionid":"b8Q1f62SdW","appinfo":{"numUsers":"6","numOnlineUsers":"120","numKeys":"1533","version":"1.0","customerPanelLink":"https:\/\/localhost\/panel\/wnelson03\/test\/"}}
```

Encoding the above JSON with my application secret `76489f2ba92ddf9132e28d56870004a62d30ec5b40eaf2071ae48036e7144b5f` on the website [https://www.devglan.com/online-tools/hmac-sha256-online](https://www.devglan.com/online-tools/hmac-sha256-online), I get the output 8d0a11b00f44bee4e563117db28533943f5170854f5f65e69470c59bffb7d0d5. In my application, I compare these and abort program if they don't match.

**For all other responses:**

For all other requests, you're going to need that string you saved earlier, `[GUID]-[secret]`

My string is \``4a59f8ca-b304-47-76489f2ba92ddf9132e28d56870004a62d30ec5b40eaf2071ae48036e7144b5f` and the JSON response is:

```json
{"success":true,"message":"Logged in!","info":{"username":"3Y8FC2-MRHKUO-U9RH8I-GNHD2U-THK4X8-PW584D","subscriptions":[{"subscription":"default","key":"3Y8FC2-MRHKUO-U9RH8I-GNHD2U-THK4X8-PW584D","expiry":"1659657607"},{"subscription":"default","key":null,"expiry":"1659749662"}],"ip":"::1","hwid":null,"createdate":"1659225608","lastlogin":"1659363059"}}
```

and the header I received was `signature: e2993347290077c90011694bf887975117bff08897106f9c501d75c48102f721`

Encoding the JSON response I received with the string I saved before I made the init request, `4a59f8ca-b304-47-76489f2ba92ddf9132e28d56870004a62d30ec5b40eaf2071ae48036e7144b5f`on the website [https://www.devglan.com/online-tools/hmac-sha256-online](https://www.devglan.com/online-tools/hmac-sha256-online), I get the same result as the signature `e2993347290077c90011694bf887975117bff08897106f9c501d75c48102f721`



There are several examples on how to encode with HMAC SHA256 [https://github.com/search?q=hmac+sha256](https://github.com/search?q=hmac+sha256)

Also you can view how the C++ example does this if you want a more specific example [https://github.com/KeyAuth/keyauth-cpp-library](https://github.com/KeyAuth/keyauth-cpp-library)
