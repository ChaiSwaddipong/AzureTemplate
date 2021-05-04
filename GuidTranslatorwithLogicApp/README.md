# GUID Translator

This Azure Logic Apps takes a sample JSON as input and converts the GUID information in it to something that is bit more user friendly like email, subscription name (as opposed to id), etc.  It can also be configured to respond to an Azure Alert, triggered by Log Analytics query.  More on that here https://docs.microsoft.com/en-us/azure/azure-monitor/alerts/tutorial-response.


Here is a typical JSON you might find:

```
{
	"Id": "32f6582c-7594-417f-9bcf-585a275ec682",
	"Properties": {
		"PrincipalId": "409c2d9f-2345-9bcf-ac4e-46f9fba61d08",
		"PrincipalType": "User",
		"RoleDefinitionId": "/providers/Microsoft.Authorization/roleDefinitions/b7e6dc6d-f1e8-4753-8033-0f276bb0955b",
		"Scope": "/subscriptions/40984ee8-6634-40a4-3214-abcf76389376/resourceGroups/rg1/providers/Microsoft.Storage/storageAccounts/sa1"
	}
}
```

The app will convert the ```PrincipalId``` and the Azure subscription ID ```40984ee8-6634-40a4-3214-abcf76389376``` to user name and subscription name. Then, it sends an email with the converted info to an operators. These operations make use the Azure ARM and Azure AD, and Outlook connectors. 


You should see a similar app in the Logic App Designer. ** Note that the ARM template will create these connectors without valid login information. You will have to edit the connectors and supply the correct credentials. **

![Image of GUID Translator](https://github.com/ChaiSwaddipong/AzureTemplate/blob/main/GuidTranslatorwithLogicApp/image1.PNG)

The email now contains user and subscription name instead of IDs. This is useful and actionable information for the end user. 

![Image of output](https://github.com/ChaiSwaddipong/AzureTemplate/blob/main/GuidTranslatorwithLogicApp/output.PNG)

More on Logic App Connectors here:
* https://docs.microsoft.com/en-us/connectors/arm/
* https://docs.microsoft.com/en-us/connectors/azuread/ 
* https://docs.microsoft.com/en-us/azure/connectors/connectors-create-api-office365-outlook