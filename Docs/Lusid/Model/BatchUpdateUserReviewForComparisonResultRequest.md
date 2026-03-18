# Finbourne.Sdk.Lusid.Model.BatchUpdateUserReviewForComparisonResultRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComparisonResultId** | **string** | Required | Comparison result identifier, encoded value for core attribute results, aggregate attribute results, reconciliation type and run instanceId. |
| **UserReviewAdd** | [GroupReconciliationUserReviewAdd](GroupReconciliationUserReviewAdd.md) | Optional | *No description available.* |
| **UserReviewRemove** | [GroupReconciliationUserReviewRemove](GroupReconciliationUserReviewRemove.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpdateUserReviewForComparisonResultRequest(
    comparisonResultId: "...",  // required — Comparison result identifier, encoded value for core attribute results, aggregate attribute results, reconciliation type and run instanceId.
    userReviewAdd: new GroupReconciliationUserReviewAdd(...),  // optional
    userReviewRemove: new GroupReconciliationUserReviewRemove(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpdateUserReviewForComparisonResultRequest>(json);
```

- [GroupReconciliationUserReviewAdd](GroupReconciliationUserReviewAdd.md)
- [GroupReconciliationUserReviewRemove](GroupReconciliationUserReviewRemove.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

