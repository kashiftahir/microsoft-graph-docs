---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewUnifiedRoleDefinition()
description := "Update basic properties of application registrations"
requestBody.SetDescription(&description) 
displayName := "Application Registration Support Administrator"
requestBody.SetDisplayName(&displayName) 


unifiedRolePermission := graphmodels.NewUnifiedRolePermission()
additionalData := map[string]interface{}{
	allowedResourceActions := []string {
		"microsoft.directory/applications/basic/read",

	}
}
unifiedRolePermission.SetAdditionalData(additionalData)

rolePermissions := []graphmodels.UnifiedRolePermissionable {
	unifiedRolePermission,

}
requestBody.SetRolePermissions(rolePermissions)
isEnabled := "true"
requestBody.SetIsEnabled(&isEnabled) 

result, err := graphClient.RoleManagement().Directory().RoleDefinitions().Post(requestBody)


```