# Enterprise Authentication in NativeScript Sidekick with OAuth 2

Getting OAuth2 info from Azure and adding those to Sidekick.

## Form Fields

First, let's take a closer look at the form fields required within NativeScript Sidekick to enable enterprise authentication using OAuth 2 for your project. Then, as an example, we'll explore how we'd complete the form for a project using Azure Active Directory.

|Field name|Description|
| ------------- |:-------------:|
|Name|The name can be anything you choose and is simply intended an an identifier to make it easier find your authentication service within the Kinvey console.|
|Provider URI|In OAuth terms, this is usually referred to as the token endpoint for the authentication service that you are connecting to|
|Grant Endpoint|In OAuth terms, this is usually referred to as the authorization endpoint for the authentication service that you are connecting to|
|Client ID|This is the public identifier for your app that is provided by the authentication service that you are connecting to. In some cases (as in our Azure example below), this may be referred to as an application ID.|
|Client Secret|This is a private app key provided by the authentication service that you are connecting to.|
|User ID Attribute|This is an optional field. In most cases, it can be left blank. It is necessary only if your authentication service places the user ID in an attrbute other than the default `id_token`.|
|User ID Endpoint|This is an optional field. In most cases, it can be left blank. It is necessary only if your authentication service requires a separate endpoint to obtain the user ID|
|Scope|stuff|
|Include client ID in token request?|stuff|
|Include client secret in token request?|stuff|

## Example - Azure Active Directory

### Setting Up Azure AD

### Enterprise Authentication Form Field Values for Azure AD