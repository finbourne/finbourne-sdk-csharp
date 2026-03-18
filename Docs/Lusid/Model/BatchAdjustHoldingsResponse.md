# Finbourne.Sdk.Lusid.Model.BatchAdjustHoldingsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, HoldingAdjustmentWithDate&gt;](HoldingAdjustmentWithDate.md) | Optional | The holdings which have been successfully adjusted. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The holdings that could not be adjusted along with a reason for their failure. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Contains warnings related to adjusted holdings |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchAdjustHoldingsResponse(
    values: new HoldingAdjustmentWithDate(...),  // optional — The holdings which have been successfully adjusted.
    failed: new ErrorDetail(...),  // optional — The holdings that could not be adjusted along with a reason for their failure.
    metadata: ,  // optional — Contains warnings related to adjusted holdings
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchAdjustHoldingsResponse>(json);
```


## Related Models

- [HoldingAdjustmentWithDate](HoldingAdjustmentWithDate.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

