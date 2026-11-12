# Finbourne.Sdk.Lusid.Model.UpsertExternalDealingEstimatesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, UpsertExternalDealingEstimateResult&gt;](UpsertExternalDealingEstimateResult.md) | Optional | A dictionary of successfully loaded sets, keyed by the request key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A dictionary of sets that could not be loaded, keyed by the request key, containing error details. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertExternalDealingEstimatesResponse(
    successes: new UpsertExternalDealingEstimateResult(...),  // optional — A dictionary of successfully loaded sets, keyed by the request key.
    failed: new ErrorDetail(...),  // optional — A dictionary of sets that could not be loaded, keyed by the request key, containing error details.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertExternalDealingEstimatesResponse>(json);
```


## Related Models

- [UpsertExternalDealingEstimateResult](UpsertExternalDealingEstimateResult.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

