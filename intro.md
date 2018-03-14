---
title: Using Enterprise Authentication
description: Learn how to connect to your enterprise authentication provider, and how to leverage data from that provider in your apps.
position: 1
publish: true
---

# Using Enterprise Authentication

NativeScript Sidekick lets you connect to existing enterprise identity and single sign-on solutions. This powerful functionality allows enterprise application developers to avoid the complexity of integrating these protocols into mobile apps, while also allowing enterprise IT to ensure that access to resources is secured only to authenticated users, as well as maintaining full control over a mobile user's identity. 

> **NOTE**: Sidekick’s enterprise authentication implementation is powered by [Progress Kinvey](https://www.kinvey.com/), a leading backend app development platform, with powerful capabilities to connect to and use enterprise data sources.

Let’s see how it all works.

## Step 1. Select an authentication service

On the Enterprise Auth screen the first thing you’ll see is a collection of radio buttons, asking you to choose between **SAML-Redirect**, **OpenID Connect**, and **OAuth 2**.

![](images/selecting-authentication-service.png)

TODO: HOW DO YOU KNOW WHICH AUTHENTICATION SERVICE YOUR ENTERPRISE IS USING111!!!!11!!!??@111!!24!!!?

## Step 2: Complete the configuration

Each authentication services requires a different set of values needed to make the connection. Therefore, refer to one of the following guides to help complete the rest of the necessary configuration.

* [Configuring **SAML-Redirect** Authentication](saml.md)
* [Configuring **OpenID Connect** Authentication](openid.md)
* [Configuring **OAuth 2** Authentication](oauth2.md)

## Step 3: Run your app

TODO: Complete this section once we have the authentication template in Sidekick and can run apps using this workflow
