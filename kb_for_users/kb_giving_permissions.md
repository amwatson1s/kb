# Giving Permissions in Azure

1. The _______@[yourdomain}.onmicrosoft.com user you create for them will be able log into portal.azure.com but they cannot do anything until they are added to a subscription. For efficiency’s sake, we suggest you do that for a multiple users all at once, so you will want to follow the steps in [this kb](https://github.com/CenturyLinkCloud/cint-documentation/blob/master/kb_for_users/kb_usercreate.md) multiple times before giving permissions.

2. To add a user to a subscription, do that navigate to https://portal.azure.com as your admin user, and find subscriptions (The key icon).

![alt text](https://github.com/CenturyLinkCloud/cint-documentation/blob/master/kb_for_users/AccessControl1.png?raw=true)

3. Click on the subscription, Access Control (IAM), then +Add 

![alt text](https://github.com/CenturyLinkCloud/cint-documentation/blob/master/kb_for_users/AccessControl2.png?raw=true)

* For the time being, we expect you to be giving everyone either Owner or Contributor roles. Select a role. 
* Once you have selected the role, you can begin locating and adding all the users you created into that role. 
Give the users the usernames and passwords you created in [this kb](https://github.com/CenturyLinkCloud/cint-documentation/blob/master/kb_for_users/kb_usercreate.md)  and they should be ready to go.

