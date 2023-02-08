---
description: >-
  Allows connections to your application from a website, granting users the
  ability to login and control the application's function
---

# Web Loader

With KeyAuth, you can allow your users to login on a website, click a button to download loader, run the loader, and then the loader will automatically connect with the website and login.

{% hint style="warning" %}
The web loader runs a HTTP server on the TCP Port 1337. Be sure to not have other programs occupying this port while web loader is running. The Razer Synapse software uses TCP port 1337 so you’ll need to close that to utilize the web loader.
{% endhint %}

Customers must log into customer panel to utilize the web loader. You’ll see your customer panel link by navigating to [https://keyauth.cc/app/?page=app-settings](https://keyauth.cc/app/?page=app-settings). If you want to put customer panel on your own domain, i.e. `example.com`, you can set that on app settings. Video [tutorial here](https://www.youtube.com/watch?v=iHQe4GLvgaE). If you want to change the design of the web loader, you could use [https://github.com/KeyAuth/Custom-Customer-Panel](https://github.com/KeyAuth/Custom-Customer-Panel)

{% code title="Program.cs" lineNumbers="true" %}
```csharp
KeyAuthApp.web_login();

Console.WriteLine("\n Waiting for button to be clicked");
KeyAuthApp.button("close");
```
{% endcode %}

Above is a C# code snippet for making web loader connection
