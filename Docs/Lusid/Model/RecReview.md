# Finbourne.Sdk.Lusid.Model.RecReview

A summary of the per-result review state across the result set.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountReviewed** | **int** | Required | The number of results with review status Reviewed. |
| **CountRequired** | **int** | Required | The number of results with review status Required. |
| **CountNotRequired** | **int** | Required | The number of results with review status Not Required. |
| **CompletionRatio** | **decimal** | Required | Reviewed / (Reviewed + Required). Is 1.0 when the denominator is zero, and null when execution failed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecReview(
    countReviewed: 0,  // required — The number of results with review status Reviewed.
    countRequired: 0,  // required — The number of results with review status Required.
    countNotRequired: 0,  // required — The number of results with review status Not Required.
    completionRatio: 0.0d  // required — Reviewed / (Reviewed + Required). Is 1.0 when the denominator is zero, and null when execution failed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecReview>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

