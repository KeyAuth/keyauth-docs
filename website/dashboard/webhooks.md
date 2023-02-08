---
description: Securely send & receive request to URL from your application
---

# Webhooks

{% hint style="danger" %}
It’s a common misconception that you should put a Discord Webhook URL in the URL field. While it’s possible to use Discord webhooks with KeyAuth webhooks, it isn’t the main use; and requires extra configuration.
{% endhint %}

First, you’re going to want to navigate to [https://keyauth.cc/app/?page=webhooks](https://keyauth.cc/app/?page=webhooks) and then click the **Add Webhook** button.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Put anything you don’t want the user of your application to be able to view or manipulate. So if you were using KeyAuth webhooks to send a request to KeyAuth SellerAPI for example, you’re going to want to ensure you have the `?sellerkey=sellerkeyhere` and `&type=whatever` set as part of the URL in the dashboard. **If you don’t do this, users of your loader would be able to delete whatever they wanted** with SellerAPI, or add keys, etc.

{% hint style="danger" %}
Read the above paragraph very carefully, so that you don't accidentally allow the attacker to deface your application.
{% endhint %}

Press Submit when you’re finished. You’ll then be shown a **Webhook ID**. Copy that ID and place in your application code as such.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Then, if you’d like, you can specify URL parameters. These are appended to the URL you submitted on the dashboard. So, if you submit the URL `https://keyauth.win/api/seller/?sellerkey=sellerKeyHere&type=banuser` on the Dashboard and then have the parameters `&user=userNameHere` in the loader, this will be appended to create the URL `https://keyauth.win/api/seller/?sellerkey=sellerKeyHere&type=banuser&user=userNameHere` which KeyAuth server will send a request to

{% code title="Program.cs" lineNumbers="true" %}
```csharp
string resp = KeyAuthApp.webhook("6uRv6YKqv1", "&user=userNameHere");
```
{% endcode %}

Additionally and also optionally, you can specify a request body and the content type. This is what you would need to do to send messages to a Discord Webhook. See C# code snippet below

{% code title="Program.cs" lineNumbers="true" %}
```csharp
string resp = KeyAuthApp.webhook("6uRv6YKqv1", "", "{\"content\": \"webhook message here\",\"embeds\": null}", "application/json"); // if Discord webhook message successful, response will be empty
```
{% endcode %}
