# Finbourne.Sdk.Lusid.Model.GroupReconciliationUserReviewAdd

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BreakCode** | **string** | Optional | The break code of the reconciliation result. |
| **MatchKey** | **string** | Optional | The match key of the reconciliation result. |
| **CommentText** | **string** | Optional | User&#39;s comment regarding the reconciliation result. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationUserReviewAdd(
    breakCode: "...",  // optional — The break code of the reconciliation result.
    matchKey: "...",  // optional — The match key of the reconciliation result.
    commentText: "..."  // optional — User&#39;s comment regarding the reconciliation result.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationUserReviewAdd>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

