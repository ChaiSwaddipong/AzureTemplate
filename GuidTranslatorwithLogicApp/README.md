# GUID Translator

This app takes a sample JSON , typically a result of Azure Alert from Log Analytics, and converts the GUID information in the alert to something that is bit more user friendly like email, subscription name (as opposed to id), etc.

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

![Image of GUID Translator](https://github.com/ChaiSwaddipong/AzureTemplate/blob/main/GuidTranslatorwithLogicApp/image1.PNG)
