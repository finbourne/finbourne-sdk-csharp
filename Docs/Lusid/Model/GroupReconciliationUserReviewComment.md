# Finbourne.Sdk.Lusid.Model.GroupReconciliationUserReviewComment

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CommentText** | **string** | Required | User&#39;s comment regarding the reconciliation result. |
| **UserId** | **string** | Optional | Id of the user who made a User Review input. |
| **AsAtAdded** | **DateTimeOffset** | Optional | The timestamp of the added User Review input. |
| **AsAtInvalid** | **DateTimeOffset** | Optional | The timestamp when User Review input became invalid e.g. because of the different attribute values within the new run. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationUserReviewComment(
    commentText: "...",  // required — User&#39;s comment regarding the reconciliation result.
    userId: "...",  // optional — Id of the user who made a User Review input.
    asAtAdded: DateTimeOffset.Now,  // optional — The timestamp of the added User Review input.
    asAtInvalid: DateTimeOffset.Now  // optional — The timestamp when User Review input became invalid e.g. because of the different attribute values within the new run.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationUserReviewComment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

