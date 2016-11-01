

# Deployment and Billing in Azure made easy with CenturyLink and Elasticbox:

CenturyLink has partnered with Microsoft in order to make things easier for customers. By becoming a Microsoft CSP we are able to connect to Azure and provide one combined bill with CenturyLink Cloud.

Following the steps below will allow customers to setup a Microsoft Azure Resource Management provider in Elasticbox allowing customers to create and deploy from Elasticbox into Microsoft Azure using the ARM template box.

___
1. Login to the [Azure portal](https://portal.azure.com/) using your CenturyLink Microsoft Account ( The one that end with `onmicrosoft.com` ). If you do not have one yet click [here](https://github.com/amwatson1s/kb/blob/master/kb_for_new/new_accounts.md) for instructions.

1. Create a new Azure `web application` 
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/portal.png?raw=true "Logo Title Text 1")

1. Copy the authorization endpoint url from Azure Portal `<oauth 2.0 authorization endpoint URL>?client_id=<application_id>` and paste it in a text-editor or a browsers adress-bar then add `?client=` at the end and finally the `application id` (click on the newly created app to see the application id) <-- You will use this URL to log-in to your app using the credentials you'll create in the next step..
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/portal2.png?raw=true)

1. Log out from all Microsoft accounts or open a *Cognito tab* in Chrome then Go to the URL you obtained at step #3 and use the credentials for your Microsoft Azure account. 
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/log_in_01.JPG?raw=true)

1. Click the accept button
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/accept.png?raw=true)

1. log back in in Azure portal and go to subscriptions tab, select the *Access Control (IAM)* and then select the *+ Add* on the new screen..
 1. select *Contributor* role
 2. select the user you just created in step #4!
And click OK!
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/portal4.png?raw=true)

1. Return to the "App Registrations" panel in Step 3. Select the app, and select "Keys" in the "Settings" panel. Give the key any name and expiration date, and select "Save." The value of the key will be generated. copy and keep the value (secret key) as you won't see it anymore once you navigate away!

1. Login to Elasticbox and create a new Azure resource manager provider with the information below.<br>
Subscription ID: The active subscription ID<br>
Client ID: The App ID used in Step 3<br>
Secret: The key value generated in Step 7<br>
Tenant: Name of Customer URL (everything after @)<br>
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/eb.png?raw=true)

9. Finished! Now it's time to start deploying and managing boxes in Elasticbox. If you cannot find a specific template that you are looking for in Elasticbox be sure to check out the [Azure github quickstart templates](https://github.com/Azure/azure-quickstart-templates).<br><br>

Developers can also creating a Microsoft Azure ARM provider in elasticbox using the Azure CLI and the steps below:<br><br>

Step 1: login to azure CLI
`azure login -u [username]@[company].onmicrosoft.com --tenant [company].onmicrosoft.com`

Step 2: Create azure ad application
`azure ad app create --name "[appname]" --home-page "http://[appname]" --identifier-uris "http://[appname]" --password "[password for app]"`

Step 3: Add a service principle to the AppId that was just created<br>
`azure ad sp create -a [app id]`

Step 4: List out the current subcriptions and find the active one<br>
`azure account list`

Step 5: Grant permissions to the service principle that was created
`azure role assignment create --objectId [object id for app] -o Owner -c /subscriptions/[subscription id]/`

Step 6: Test login with service principle
`azure login -u "[app id]" -p "[app password" --service-principal --tenant "[company].onmicrosoft.com"`

Step 7: Login to Elasticbox and create a service provider.
