# Finbourne.Sdk.Lusid.Model.UpsertWithholdingTaxRateRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesIdentifiers** | **Dictionary&lt;string, Object&gt;** | Optional | The series identifiers that, with effectiveAt, identify the rate row: taxCountry, profileType and the dataset&#39;s own matching dimensions, structured according to its field schema. ruleSource is not accepted here: pass it as the ruleSource query parameter, which applies it to every row in the batch, and omit it for rows that apply at every source. |
| **EffectiveAt** | **string** | Required | The effectiveAt or cut-label datetime of the DataPoint. |
| **ValueFields** | **Dictionary&lt;string, Object&gt;** | Required | The values associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |
| **MetaDataFields** | **Dictionary&lt;string, Object&gt;** | Optional | The metadata associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertWithholdingTaxRateRequest(
    seriesIdentifiers: ,  // optional — The series identifiers that, with effectiveAt, identify the rate row: taxCountry, profileType and the dataset&#39;s own matching dimensions, structured according to its field schema. ruleSource is not accepted here: pass it as the ruleSource query parameter, which applies it to every row in the batch, and omit it for rows that apply at every source.
    effectiveAt: "...",  // required — The effectiveAt or cut-label datetime of the DataPoint.
    valueFields: ,  // required — The values associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
    metaDataFields:   // optional — The metadata associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertWithholdingTaxRateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

