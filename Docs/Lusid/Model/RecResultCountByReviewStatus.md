# Finbourne.Sdk.Lusid.Model.RecResultCountByReviewStatus

Result counts broken down by review status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Required** | **int** | Required | The number of results with review status Required. |
| **NotRequired** | **int** | Required | The number of results with review status Not Required. |
| **Reviewed** | **int** | Required | The number of results with review status Reviewed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultCountByReviewStatus(
    required: 0,  // required — The number of results with review status Required.
    notRequired: 0,  // required — The number of results with review status Not Required.
    reviewed: 0  // required — The number of results with review status Reviewed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultCountByReviewStatus>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

