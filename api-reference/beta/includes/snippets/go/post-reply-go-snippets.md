---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewReplyPostRequestBody()
post := graphmodels.NewPost()
body := graphmodels.NewItemBody()
content := "content-value"
body.SetContent(&content) 
post.SetBody(body)
receivedDateTime , err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
post.SetReceivedDateTime(&receivedDateTime) 
hasAttachments := true
post.SetHasAttachments(&hasAttachments) 
from := graphmodels.NewRecipient()
emailAddress := graphmodels.NewEmailAddress()
name := "name-value"
emailAddress.SetName(&name) 
address := "address-value"
emailAddress.SetAddress(&address) 
from.SetEmailAddress(emailAddress)
post.SetFrom(from)
sender := graphmodels.NewRecipient()
emailAddress := graphmodels.NewEmailAddress()
name := "name-value"
emailAddress.SetName(&name) 
address := "address-value"
emailAddress.SetAddress(&address) 
sender.SetEmailAddress(emailAddress)
post.SetSender(sender)
conversationThreadId := "conversationThreadId-value"
post.SetConversationThreadId(&conversationThreadId) 


recipient := graphmodels.NewRecipient()
additionalData := map[string]interface{}{
emailAddress := graphmodels.New()
name := "name-value"
emailAddress.SetName(&name) 
address := "address-value"
emailAddress.SetAddress(&address) 
	recipient.SetEmailAddress(emailAddress)
}
recipient.SetAdditionalData(additionalData)

newParticipants := []graphmodels.Recipientable {
	recipient,

}
post.SetNewParticipants(newParticipants)
conversationId := "conversationId-value"
post.SetConversationId(&conversationId) 
createdDateTime , err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
post.SetCreatedDateTime(&createdDateTime) 
lastModifiedDateTime , err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
post.SetLastModifiedDateTime(&lastModifiedDateTime) 
changeKey := "changeKey-value"
post.SetChangeKey(&changeKey) 
categories := []string {
	"categories-value",

}
post.SetCategories(categories)
id := "id-value"
post.SetId(&id) 
inReplyTo := graphmodels.NewinReplyTo()
post.SetInReplyTo(inReplyTo)


attachment := graphmodels.NewAttachment()
"@odata.type" := "#microsoft.graph.fileAttachment"
attachment.Set"@odata.type"(&"@odata.type") 
lastModifiedDateTime , err := time.Parse(time.RFC3339, "2016-10-19T10:37:00Z")
attachment.SetLastModifiedDateTime(&lastModifiedDateTime) 
name := "name-value"
attachment.SetName(&name) 
contentType := "contentType-value"
attachment.SetContentType(&contentType) 
size := int32(99)
attachment.SetSize(&size) 
isInline := true
attachment.SetIsInline(&isInline) 
id := "id-value"
attachment.SetId(&id) 

attachments := []graphmodels.Attachmentable {
	attachment,

}
post.SetAttachments(attachments)
requestBody.SetPost(post)

graphClient.GroupsById("group-id").ThreadsById("conversationThread-id").PostsById("post-id").Reply().Post(requestBody)


```