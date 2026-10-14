# Finbourne.Sdk.Lusid.Model.WithholdingTaxRateResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RelationalDatasetDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SeriesIdentifiers** | [Dictionary&lt;string, RelationalDataPointFieldValueResponse&gt;](RelationalDataPointFieldValueResponse.md) | Required | The identifiers that uniquely define this DataSeries, if any, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effectiveAt or cut-label datetime of the DataPoint. |
| **ValueFields** | [Dictionary&lt;string, RelationalDataPointFieldValueResponse&gt;](RelationalDataPointFieldValueResponse.md) | Required | The values associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |
| **MetaDataFields** | [Dictionary&lt;string, RelationalDataPointFieldValueResponse&gt;](RelationalDataPointFieldValueResponse.md) | Required | The metadata associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |
| **EffectiveAtEntered** | **string** | Required | The effectiveAt datetime as entered when the DataPoint was created. |
| **DataPointVersion** | [DataPointVersion](DataPointVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxRateResponse(
    relationalDatasetDefinitionId: new ResourceId(...),  // required
    seriesIdentifiers: new RelationalDataPointFieldValueResponse(...),  // required — The identifiers that uniquely define this DataSeries, if any, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
    effectiveAt: DateTimeOffset.Now,  // required — The effectiveAt or cut-label datetime of the DataPoint.
    valueFields: new RelationalDataPointFieldValueResponse(...),  // required — The values associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
    metaDataFields: new RelationalDataPointFieldValueResponse(...),  // required — The metadata associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
    effectiveAtEntered: "...",  // required — The effectiveAt datetime as entered when the DataPoint was created.
    dataPointVersion: new DataPointVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxRateResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [RelationalDataPointFieldValueResponse](RelationalDataPointFieldValueResponse.md) — used in `SeriesIdentifiers`
- [RelationalDataPointFieldValueResponse](RelationalDataPointFieldValueResponse.md) — used in `ValueFields`
- [RelationalDataPointFieldValueResponse](RelationalDataPointFieldValueResponse.md) — used in `MetaDataFields`
- [DataPointVersion](DataPointVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

