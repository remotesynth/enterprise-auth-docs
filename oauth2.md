---
title: Configuring OAuth 2 Authentication
description: Learn how to configure and connect to an enterprise identity provider using OAuth 2.
position: 2
publish: true
---

# Configuring OAuth 2 Authentication

TODO: Super brief introduction to OAuth.

NativeScript Sidekick gives you the ability to connect to enterprise authentication providers via OAuth 2. In this article we’ll look at the various data points NativeScript Sidekick needs to make the connection, and then look at a concrete example of a sample connection using Microsoft Azure.

## Configuring your connection

The first thing you need to do to configure an OAuth 2 connection is to visit the **Enterprise Auth** screen and select the **OAuth 2** radio button. You should see a form that looks like this.

![](images/oauth-form.png)

Let’s start by looking at the fields you need to provide to connect to your enterprise authentication provider. Then, as an example, we'll explore how we'd complete the form for a project using Azure Active Directory.

## Form Fields

Here is a list of the fields you need to provide in Sidekick, and a brief description of what they are.

|Field name|Description|
| ------------- |:-------------:|
|Name|The name can be anything you choose and is simply intended an an identifier to make it easier find your authentication service within the Kinvey console.|
|Provider URI|In OAuth terms, this is usually referred to as the token endpoint for the authentication service that you are connecting to|
|Grant Endpoint|In OAuth terms, this is usually referred to as the authorization endpoint for the authentication service that you are connecting to|
|Client ID|This is the public identifier for your app that is provided by the authentication service that you are connecting to. In some cases (as in our Azure example below), this may be referred to as an application ID.|
|Client Secret|This is a private app key provided by the authentication service that you are connecting to.|
|User ID Attribute|This is an optional field. In most cases, it can be left blank. It is necessary only if your authentication service places the user ID in an attrbute other than the default `id_token`.|
|User ID Endpoint|This is an optional field. In most cases, it can be left blank. It is necessary only if your authentication service requires a separate endpoint to obtain the user ID|
|Scope|The scope defines what information your app requires access to from the OAuth authentication service provider. The specific scopes that you are requesting access to are displayed to the user by the provider when granting the authentication request. For example, a value of `profile` may indicate that you are requesting access to read the user's basic profile info from the authentication service while a value of `email` could indicate that you are requesting access to read their email address.|
|Include client ID in token request?|This is typically fine with the default of No, but some authentication providers require that you pass the client ID in the token request rather than the authorization header.|
|Include client secret in token request?|This is typically fine with the default of No, but some authentication providers require that you pass the client secret in the token request rather than the authorization header.|

Once all the fields are filled in appropriately, click the "Save Service" button to continue.

## Example - Azure Active Directory

While general field descriptions can be useful, it can be really helpful to see what this looks like in a real-world scenario. In this example, we'll set up Azure Active Directory and fill out the form with the values required to connect it within the Enterprise Authentication form in NativeScript Sidekick.

### Setting Up Azure AD

The following steps will walk you through creating a new Azure Active Directory from scratch. If you already have Azure AD set up, simply skip the first step.

1. From within the [Azure portal](https://portal.azure.com), click on Azure Active Directory or click on +New and search for Azure Active Directory.

	![Azure AD](images/AzureAD.png)

2. Choose the "App Registrations" option and "New Application Registration".
	
	![App registrations](images/new-app-registration.png)
	
3. Enter a name for the application (this can be any name you prefer), choose "Web app / API" and, for the Sign-on URL, enter `https://auth.kinvey.com`.

	![new app registration](images/create-application.png)

4. Once it is created, choose "Reply URLs".

	![application settings](images/application-settings.png)

5. Enter `https://auth.kinvey.com/oauth2/redirect` (see the [Kinvey docs](https://devcenter.kinvey.com/html5/guides/mobile-identity-connect#ConfiguringyourOAuth2IdentityProvidertoacceptKinveyRequests) for additional details)

	![Reply URLs](images/reply-urls.png)

6. Back in the application settings, choose "Required Permissions" and then "Windows Azure Active Directory".

	![required permissions](images/required-permissions.png)

7. Enable the following:

	* Access the directory as the signed-in user
	* Read all users' basic profiles
	* Sign in and read user profile

	![enable access](images/enable-access.png)

8. Back in the application settings again, choose "Keys" and create a new option under "Passwords". Set the description (this can be any text you prefer) and expiration (for example, "never"). Click "Save". Be sure to copy the key's value before leaving.

	![client secret](images/client-secret.png)

In order to test the log in process, Azure Active Directory will need a user. To add a user, go to Active Directory, click "Users and Groups", then "All Users", and finally "New User". For testing purposes, you could add yourself.

### Enterprise Authentication Form Field Values for Azure

* **Name**: Any name you choose.
* **Provider URI** and **Grant Endpoint**: To get these values from within Azure, go to Azure Active Directory, choose "App registrations" and then "Endpoints".

  ![Choosing the endpoints](images/endpoints1.png)

  On the subsequent page, the Provider URI is the OAuth 2.0 Token Endpoint value and the Grant Enpoint is the  OAuth 2.0 Authorization Endpoint value.

  ![Endpoints list](images/endpoints2.png)

* **Client ID** is the application ID found by going to Azure Active Directory and then choosing "App registrations".

  ![Application ID](images/applicationID.png)

* **Client Secret** is the value of the key created in step 8 above. If you did not copy the key during that step, it is hidden and you'll simply need to create a new key.
* **User ID Attribute** and **User ID Endpoint** can both be blank.
* **Scope** should be set to `email` to give your app access to the user's email address.
* **Include client ID in token request?** and **Include client secret in token request?** can both remain "No".

Click the "Save Service" button and you are ready to move on to building and testing your NativeScript mobile app.