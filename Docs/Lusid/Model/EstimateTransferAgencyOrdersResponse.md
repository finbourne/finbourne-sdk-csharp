# Finbourne.Sdk.Lusid.Model.EstimateTransferAgencyOrdersResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, TransferAgencyOrderEstimateResult&gt;](TransferAgencyOrderEstimateResult.md) | Optional | A dictionary of successfully estimated orders, keyed by the request key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A dictionary of failed estimates, keyed by the request key, containing error details. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EstimateTransferAgencyOrdersResponse(
    successes: new TransferAgencyOrderEstimateResult(...),  // optional — A dictionary of successfully estimated orders, keyed by the request key.
    failed: new ErrorDetail(...),  // optional — A dictionary of failed estimates, keyed by the request key, containing error details.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EstimateTransferAgencyOrdersResponse>(json);
```


## Related Models

- [TransferAgencyOrderEstimateResult](TransferAgencyOrderEstimateResult.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

