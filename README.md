# Azure Static Web App /w Azure B2C Authentication

A basic HTML only web application hosted in
[Azure Static Web Apps](https://learn.microsoft.com/en-us/azure/static-web-apps/)
using
[Azure Active Directory B2C](https://learn.microsoft.com/en-us/azure/active-directory-b2c/)
for authentication.

## Prerequisites

> Install [Static Web Apps CLI](https://azure.github.io/static-web-apps-cli/)
> for deploying Azure Static Web Apps.

## Instructions

1. Follow the instructions to create an
   [Azure AD B2C Tenant](https://learn.microsoft.com/en-us/azure/active-directory-b2c/tutorial-create-tenant).

2. Follow the instructions to configure
   [Azure AD B2C for an Azure Static Web App](https://learn.microsoft.com/en-us/azure/active-directory-b2c/configure-authentication-in-azure-static-app)

   _Only the "Sign up - Sign In" user flow is necessary_

   **Important!**

   Configure the user attributes and application claims to be collected on user
   sign up and returned in the application token. These selections ensure that
   the expected email or name claims are returned to the applcation.

   Select **"Display Name"** and **"Email Address"** from Azure Portal -> Azure
   AD B2C -> User Flows -> B2C_1_signupsignin -> Settings -> **User attributes**

   Select **"Display Name"**, **"Email Address"** and **"Identity Provider
   Access Token"** from Azure Portal -> Azure AD B2C -> User Flows ->
   B2C_1_signupsignin -> Settings -> **Application claims**

## Deploy the app

1. Deploy the SWA with `swa deploy`
1. Verify you can access the website

   ```bash
   Deploying project to Azure Static Web Apps...
   ✔ Project deployed to https://victorious-stone-02ae20de1.1.azurestaticapps.net 🚀
   ```

1. Set the Static Web App's Hosting Plan to Standard
1. Follow the Login link to verify Azure Active Directory B2C works by signing
   up with an email address and completing the required user attribute fields.

### _\~fin\~_
