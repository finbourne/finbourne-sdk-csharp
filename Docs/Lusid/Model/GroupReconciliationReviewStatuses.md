# Finbourne.Sdk.Lusid.Model.GroupReconciliationReviewStatuses

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountPending** | **int** | Required | The number of comparison results of reviewStatus \&quot;Pending\&quot; with this instanceId and reconciliationType |
| **LinkPending** | [Link](Link.md) | Required | *No description available.* |
| **CountReviewed** | **int** | Required | The number of comparison results of reviewStatus \&quot;Reviewed\&quot; with this instanceId and reconciliationType |
| **LinkReviewed** | [Link](Link.md) | Required | *No description available.* |
| **CountMatched** | **int** | Required | The number of comparison results of reviewStatus \&quot;Matched\&quot; with this instanceId and reconciliationType |
| **LinkMatched** | [Link](Link.md) | Required | *No description available.* |
| **CountInvalid** | **int** | Required | The number of comparison results of reviewStatus \&quot;Invalid\&quot; with this instanceId and reconciliationType |
| **LinkInvalid** | [Link](Link.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationReviewStatuses(
    countPending: 0,  // required — The number of comparison results of reviewStatus \&quot;Pending\&quot; with this instanceId and reconciliationType
    linkPending: new Link(...),  // required
    countReviewed: 0,  // required — The number of comparison results of reviewStatus \&quot;Reviewed\&quot; with this instanceId and reconciliationType
    linkReviewed: new Link(...),  // required
    countMatched: 0,  // required — The number of comparison results of reviewStatus \&quot;Matched\&quot; with this instanceId and reconciliationType
    linkMatched: new Link(...),  // required
    countInvalid: 0,  // required — The number of comparison results of reviewStatus \&quot;Invalid\&quot; with this instanceId and reconciliationType
    linkInvalid: new Link(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationReviewStatuses>(json);
```

- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

