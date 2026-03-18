# Finbourne.Sdk.Lusid.Model.GroupReconciliationUserReview

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BreakCodes** | [List&lt;GroupReconciliationUserReviewBreakCode&gt;](GroupReconciliationUserReviewBreakCode.md) | Optional | A list of break codes shared between the reconciliation runs of the same run instance and result hash. |
| **MatchKeys** | [List&lt;GroupReconciliationUserReviewMatchKey&gt;](GroupReconciliationUserReviewMatchKey.md) | Optional | A list of match keys shared between the reconciliation runs of the same run instance and result hash. |
| **Comments** | [List&lt;GroupReconciliationUserReviewComment&gt;](GroupReconciliationUserReviewComment.md) | Optional | A list of comments shared between the reconciliation runs of the same run instance and result hash. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationUserReview(
    breakCodes: new List<GroupReconciliationUserReviewBreakCode>(),  // optional — A list of break codes shared between the reconciliation runs of the same run instance and result hash.
    matchKeys: new List<GroupReconciliationUserReviewMatchKey>(),  // optional — A list of match keys shared between the reconciliation runs of the same run instance and result hash.
    comments: new List<GroupReconciliationUserReviewComment>()  // optional — A list of comments shared between the reconciliation runs of the same run instance and result hash.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationUserReview>(json);
```


## Related Models

- [GroupReconciliationUserReviewBreakCode](GroupReconciliationUserReviewBreakCode.md) — used in `BreakCodes`
- [GroupReconciliationUserReviewMatchKey](GroupReconciliationUserReviewMatchKey.md) — used in `MatchKeys`
- [GroupReconciliationUserReviewComment](GroupReconciliationUserReviewComment.md) — used in `Comments`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

