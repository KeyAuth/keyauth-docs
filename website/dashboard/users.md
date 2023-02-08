---
description: All of the users on an application
---

# Users

## Create User

When creating a user you will be asked to provide the following:

1. Username - The username you would like to set,
2. Password - The password you would like to set,&#x20;
3. Subscription - The subscription you would like the user to have,&#x20;
4. Subscription Expiry - The expiration of the subscription,

## Set Variable

If you would like to assign a user variable you will be asked to provide the following:

1. User - Which user would you like to apply this too? (Select one or all)
2. Variable - The variable name you would like to assign,
3. Variable data - This is the actual data that is being assigned to the Variable on the user

## Import Users

If you are coming from another service or if you created users somewhere else you can import users by inserting data in the following format: (username, hwid, daysToExpire)

{% hint style="info" %}
"|" is the separator you will need to use if you are importing multiple users. The HWID is the hardware ID of the user.&#x20;
{% endhint %}

## Extend User(s)

If you would like to extend the expiration for users you can do so by providing the following:

1. User - Which user(s) would you like to extend? (if not all)
2. Subscription - Which subscription is being applied?,&#x20;
3. Unit of time to add - (seconds, minutes, hours, days, etc),
4. Time to add - This number is multiplied by the unit of time you select to add,&#x20;
5. Active users only - If selected, only active users will be extended

## Delete All Users

This will delete all of the users on the application.&#x20;

{% hint style="danger" %}
Deleting all users can not be undone.&#x20;
{% endhint %}

## Delete Expired Users

This will delete all of the expired users on the application.

{% hint style="danger" %}
Deleting all expired users can not be undone.&#x20;
{% endhint %}

## HWID Reset All Users

Reset the HWID (hardware ID for all users on the selected application)

{% hint style="danger" %}
Resetting the HWID for all users can not be undone.
{% endhint %}

## Created User(s) in Table

When a user is created, they will appear in a table. The table will show the following information about the user:&#x20;

1. Username - The username of the user,
2. HWID - The HWID of the user,
3. IP - The IP of the user,
4. Last Login Date - The last time the user logged on,
5. Banned - The ban status of the user,
6. Actions - The actions dropdown gives the ability to delete. reset hwid, ban, pause, unpause, and edit the user.





