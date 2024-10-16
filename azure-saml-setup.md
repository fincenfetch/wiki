# Azure - Auth0 Connect

#### Azure setup:
1. Open [portal.azure.com](portal.azure.com).
2. Go to Azure Active Directory > Enterprise applications > + New Application.
3. Now click + Create your own application.
4. For convenience, put AzureViaSaml under the What’s the name of your app?.
5. Under What are you looking to do with your application? select the Integrate any other application you don’t find in the gallery (Non-gallery) and click Create.
6. Now click Single sign-on in the left pane, and under Select a single sign-on method, select SAML.
7. In the 1. Basic SAML Configuration box, click Edit.
8. Under Identifier (Entity ID), set up the identifier as per this example: urn:auth0:tenant-name:connection-name.
* NOTE: The connection doesn’t exist in Auth0 at this point, so choose any name. In this example, let’s name the connection AzureViaSaml. The resulting identifier will be urn:auth0:my-tenant:AzureViaSaml
9. Set the Reply URL (Assertion Consumer Service URL) to https://fincenfetch.us.auth0.com/login/callback
	* https://fincenfetch.auth0.com/login/callback if the tenant was created before 11 June 2020.
10. Click Save.
11. In the 3. SAML Signing Certificate box click Download next to Certificate (Base64).
12. In the 4. Set up AzureViaSaml box, copy the Login URL. It will look like https://login.microsoftonline.com/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/saml2
13. Complete the Auth0 Setup.

#### Azure  Assign users and groups to app-roles for your application:
1. Click on Users and groups on the left pane of the Enterprise Application
2. Click on Add user/group
3. Select the Users to be assigned to this Application

#### Auth0 Setup:
1. Go to [Dashboard > Authentication > Enterprise > SAML > + Create connection](https://manage.auth0.com/#/connections/enterprise/samlp/create)
2. Set the name to AzureViaSaml.
3. Set the Sign In URL and the Sign Out URL value to the link copied in Step 12 in Azure setup (e.g., https://login.microsoftonline.com/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/saml2).
4. Upload the X509 Signing Certificate (Base64) that was downloaded from Azure in Step 11.
5. Click Create.

#### Auth0 Setup:
1. Under [Dashboard > Authentication > Enterprise > SAML select the Connection](https://manage.auth0.com/#/connections/enterprise/samlp)
2. On the ‘Applications’ tab, assign an Application to this Connection
- Another option is to navigate to [Dashboard > Authentication > Enterprise > SAML](https://manage.auth0.com/#/connections/enterprise/samlp), click three dots next to the connection just created, and select Try.