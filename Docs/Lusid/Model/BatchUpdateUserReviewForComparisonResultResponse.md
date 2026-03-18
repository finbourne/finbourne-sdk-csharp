# Finbourne.Sdk.Lusid.Model.BatchUpdateUserReviewForComparisonResultResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, GroupReconciliationComparisonResult&gt;](GroupReconciliationComparisonResult.md) | Optional | The collection of comparison results that have been successfully updated. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The collection of comparison results that could not be updated with the provided user input along with a reason for their failure. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Contains warnings related to the updated comparison result user input |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpdateUserReviewForComparisonResultResponse(
    values: new GroupReconciliationComparisonResult(...),  // optional — The collection of comparison results that have been successfully updated.
    failed: new ErrorDetail(...),  // optional — The collection of comparison results that could not be updated with the provided user input along with a reason for their failure.
    metadata: ,  // optional — Contains warnings related to the updated comparison result user input
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpdateUserReviewForComparisonResultResponse>(json);
```


## Related Models

- [GroupReconciliationComparisonResult](GroupReconciliationComparisonResult.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

