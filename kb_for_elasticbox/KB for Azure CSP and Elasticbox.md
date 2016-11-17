

# Deployment and Billing in Azure made easy with CenturyLink and Elasticbox:

CenturyLink has partnered with Microsoft in order to make things easier for customers. By becoming a Microsoft CSP we are able to connect to Azure and provide one combined bill with CenturyLink Cloud.

Following the steps below will allow customers to setup a Microsoft Azure Resource Management provider in Elasticbox allowing customers to create and deploy from Elasticbox into Microsoft Azure using the ARM template box.

___
1. Login to the [Azure portal](https://portal.azure.com/) using your CenturyLink Microsoft Account ( The one that end with `onmicrosoft.com` ). If you do not have one yet click [here](https://github.com/amwatson1s/kb/blob/master/kb_for_new/new_accounts.md) for instructions.

1. Create a new Azure application in the Azure Active Directory. <b>Be sure to select "Native" when selecting the application type.</b>
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/portal.png?raw=true "Logo Title Text 1")

1. Verify the application was inserted in the Azure Active Directory by checking the application details.
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/verify.png?raw=true)

1. Log back in to the Azure portal and go to subscriptions tab, select the *Access Control (IAM)* and then select the *+ Add* on the new screen..
 1. select *Contributor* role
 2. Search for the application you just created in step #2!
And click OK!
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/portal4.png?raw=true)

1. Return to the "App Registrations" panel in Step 2. Select the app, and select "Keys" in the "Settings" panel. Give the key any name and expiration date, and select "Save." The value of the key will be generated. copy and keep the value (secret key) as you won't see it anymore once you navigate away!

1. Login to Elasticbox and create a new Azure resource manager provider with the information below.<br>
Subscription ID: The active subscription ID<br>
Client ID: The Application ID<br>
Secret: The key value generated in Step 5<br>
Tenant: Name of Customer URL (everything after @)<br>
![alt text](https://github.com/amwatson1s/kb/blob/master/kb_for_elasticbox/eb.png?raw=true)

1. Finished! Now it's time to start deploying and managing boxes in Elasticbox. If you cannot find a specific template that you are looking for in Elasticbox be sure to check out the [Azure github quickstart templates](https://github.com/Azure/azure-quickstart-templates).<br><br>

