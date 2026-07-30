# Finbourne.Sdk.Lusid.Model.RecRequestedResultRevision

A result flagged for re-review as part of a Request Revisions decision.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecResultId** | **string** | Required | The identifier of the result to flag for re-review. |
| **CommentText** | **string** | Optional | An optional per-result comment added to the result&#39;s user comments. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecRequestedResultRevision(
    recResultId: "...",  // required — The identifier of the result to flag for re-review.
    commentText: "..."  // optional — An optional per-result comment added to the result&#39;s user comments.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecRequestedResultRevision>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

