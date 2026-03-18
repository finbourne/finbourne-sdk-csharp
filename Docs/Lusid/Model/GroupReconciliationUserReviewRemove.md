# Finbourne.Sdk.Lusid.Model.GroupReconciliationUserReviewRemove

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BreakCodeAsAtAdded** | **DateTimeOffset?** | Optional | The timestamp of the added User Review input. |
| **MatchKeyAsAtAdded** | **DateTimeOffset?** | Optional | The timestamp of the added User Review input. |
| **CommentTextAsAtAdded** | **DateTimeOffset?** | Optional | The timestamp of the added User Review input. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationUserReviewRemove(
    breakCodeAsAtAdded: DateTimeOffset.Now,  // optional — The timestamp of the added User Review input.
    matchKeyAsAtAdded: DateTimeOffset.Now,  // optional — The timestamp of the added User Review input.
    commentTextAsAtAdded: DateTimeOffset.Now  // optional — The timestamp of the added User Review input.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationUserReviewRemove>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

