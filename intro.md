---
title: Using Enterprise Authentication
description: Learn how to connect to your enterprise authentication provider, and how to leverage data from that provider in your apps.
position: 1
publish: true
---

# Using Enterprise Authentication

NativeScript Sidekick lets you connect to existing enterprise identity and single sign-on solutions. This powerful functionality allows application developers to leverage enterprise user accounts, and to do so while avoiding the complexity of integrating these protocols into mobile apps.

This functionality also allows enterprise IT to ensure that access to resources is secured only to authenticated users, as well as maintaining full control over a mobile user's identity. 

> **NOTE**: Sidekick’s enterprise authentication implementation is powered by [Progress Kinvey](https://www.kinvey.com/), a leading backend app development platform, with powerful capabilities to connect to and use enterprise data sources.

Let’s see how it all works.

## Step 1. Select an authentication service

On the Enterprise Auth screen the first thing you’ll see is a collection of radio buttons, asking you to choose between **SAML-Redirect**, **OpenID Connect**, and **OAuth 2**.

![](images/selecting-authentication-service.png)

Knowing which service you need means knowing a little bit about your enterprise authentication provider. Some providers only support one of the above protocols, while others allow you to choose between the protocol you prefer.

Once you’ve figured out which protocol your service supports, select the appropriate radio button and move on to the next step.

## Step 2: Complete the configuration

Each authentication services requires a different set of values needed to make the connection. Therefore, refer to one of the following guides to help complete the rest of the necessary configuration.

* [Configuring **SAML-Redirect** Authentication](saml.md)
* [Configuring **OpenID Connect** Authentication](openid.md)
* [Configuring **OAuth 2** Authentication](oauth2.md)

## Step 3: Run your app

After you’ve completed the authentication setup, your last step is to run your app and see your new authentication workflow in action.

> **TIP**: If you haven’t run an app on a device using NativeScript Sidekick before, check out the documentation on [running your app](https://docs.nativescript.org/sidekick/user-guide/run-app/run-app-on-device).

After Sidekick deploys your new app to your device(s) you should see an app that looks like this.

![](images/template-in-action.png)

When you tap the **Log in** button, if all went well, you should be prompted to authenticate with your enterprise authentication provider. In the case of our Microsoft Azure-based example, the app prompts the user to authenticate with their Microsoft account.

![](images/app-auth-screen.png)

> **NOTE**: Configuring enterprise authentication providers is very tricky. If you’re not seeing your auth screen as expected, or if you hit problems at any time throughout the process, feel free to [react out on the NativeScript community forum](https://discourse.nativescript.org/c/Sidekick).

And that’s it! You’ve now successfully built an app that can connect to an enterprise authentication provider.
