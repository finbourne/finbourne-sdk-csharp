# Finbourne.Sdk.Lusid.Model.UpsertRelationalDataPointRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataSeries** | [DataSeries](DataSeries.md) | Required | *No description available.* |
| **EffectiveAt** | **string** | Required | The effectiveAt or cut-label datetime of the DataPoint. |
| **ValueFields** | **Dictionary&lt;string, Object&gt;** | Required | The values associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |
| **MetaDataFields** | **Dictionary&lt;string, Object&gt;** | Optional | The metadata associated with the DataPoint, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertRelationalDataPointRequest(
    dataSeries: new DataSeries(...),  // required
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
var instance = JsonConvert.DeserializeObject<UpsertRelationalDataPointRequest>(json);
```


## Related Models

- [DataSeries](DataSeries.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

