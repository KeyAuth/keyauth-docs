---
description: Tutorial on how to register & use Security Keys such as YubiKey on KeyAuth
---

# Setup YubiKey/Security Key



Security keys are a more secure method of 2FA. Unlike 2FA, the data stored in the servers' database is of no use to an attacker. The private key which is crucial to authentication is stored on the security key itself.&#x20;

Furthermore, security keys will lock on to the domain of the website it's registered on. This will prevent you from falling victim to a phishing attack. If you enter your security key on a fake website, the attacker will be unable to authenticate on the real website with the response from the security key.



Navigate to [https://keyauth.cc/app/?page=account-settings](https://keyauth.cc/app/?page=account-settings)

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Here click the security keys button.

Specify a name for the security key. We recommend something that will remind you which key it is. It is recommended that you register multiple security keys in case you lose one of them.



Once you've selected a name, click the **Register** button. You'll be prompted to insert your security key and tap it, please do that.

Now, your security key has been registered to your KeyAuth account.&#x20;

{% hint style="warning" %}
You must login with one of the security keys that has been registered to your account. Attempting to use a security key you haven't registered to your account will **not work**.
{% endhint %}

When you login to the KeyAuth dashboard the next time, you'll be prompted to insert your security key and tap it. Please do that and if the inputted security key matches one of the ones registered to your account, you'll be redirected to dashboard.



Thanks for using KeyAuth and taking the time to further secure your account.

