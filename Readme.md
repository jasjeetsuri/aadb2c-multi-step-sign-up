# Azure AD B2C: Multi steps sign-up policy
This sample custom policy demonstrates sign-up with multi steps. When a user clicks on create new account, Azure AD B2C presents the first sign-up page. The first page collects the user name and password, and making a call to REST API to check if user already exists in the directory. Also the REST API copy the newPassword claim to stringPassword. So, you can defer the creating of the user to the second page.

On the second page, B2C asks the user to provide additional information. In this demo, the display name, first name, and last name. Clicking on continue creates the account in the directory 

You can use this policy to display 'Terms of service' or 'Privacy', on a separated page, before the account is created.

## Disclaimer
The sample policy is developed and managed by the open-source community in GitHub. This policy is not part of Azure AD B2C product and it's not supported under any Microsoft standard support program or service. The policy is provided AS IS without warranty of any kind.

### Application Settings
To test the policy, you need to deploy the Restful API solution (C# .Net core). Open the `AADB2C.MultiStepSignUp.sln` Visual Studio solution in Visual Studio. In the `AADB2C.MultiStepSignUp` project, open the `appsettings.json`. Replace the app settings with your own values:
```JSON
"AppSettings": {
    "Tenant": "<Your Azure AD B2C tenant name>",
    "ClientId": "<Your Azure AD Graph app ID>",
    "ClientSecret": "<Your Azure AD Graph app secret>"
  }
```

After you change the setting, deploy the solution to Azure App Services. For more information, see: [Publish an ASP.NET Core app to Azure with Visual Studio](https://docs.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)

> Note:  This sample policy is based on [SocialAndLocalAccounts starter pack](https://github.com/Azure-Samples/active-directory-b2c-custom-policy-starterpack/tree/master/SocialAndLocalAccounts). All changes are marked with **Demo:** comment inside the policy XML files. Make the nessacery changes in the **Demo action required** sections.
