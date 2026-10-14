# Finbourne.Sdk.Lusid.Model.DeleteWithholdingTaxRateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesIdentifiers** | **Dictionary&lt;string, Object&gt;** | Optional | The identifiers that uniquely define this DataSeries, if any, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |
| **EffectiveAt** | **string** | Required | The effectiveAt or cut-label datetime of the DataPoint. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteWithholdingTaxRateRequest(
    seriesIdentifiers: ,  // optional — The identifiers that uniquely define this DataSeries, if any, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
    effectiveAt: "..."  // required — The effectiveAt or cut-label datetime of the DataPoint.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteWithholdingTaxRateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

