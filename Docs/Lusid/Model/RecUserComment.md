# Finbourne.Sdk.Lusid.Model.RecUserComment

A user-authored comment attached to a rec result. Carried forward with the result across runs.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CommentId** | **string** | Required | System-generated GUID identifying the comment. Set once on creation. |
| **CommentText** | **string** | Required | The body of the comment. |
| **UserId** | **string** | Required | The author of the comment. |
| **AsAtCreated** | **DateTimeOffset** | Required | The asAt time the comment was created. Set once. |
| **AsAtModified** | **DateTimeOffset** | Required | The asAt time the comment was last modified. Equals asAtCreated until the first edit. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecUserComment(
    commentId: "...",  // required — System-generated GUID identifying the comment. Set once on creation.
    commentText: "...",  // required — The body of the comment.
    userId: "...",  // required — The author of the comment.
    asAtCreated: DateTimeOffset.Now,  // required — The asAt time the comment was created. Set once.
    asAtModified: DateTimeOffset.Now  // required — The asAt time the comment was last modified. Equals asAtCreated until the first edit.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecUserComment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

