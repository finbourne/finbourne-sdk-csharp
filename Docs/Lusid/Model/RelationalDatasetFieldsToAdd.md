# Finbourne.Sdk.Lusid.Model.RelationalDatasetFieldsToAdd

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesIdentifiers** | [List&lt;CreateSeriesIdentifierField&gt;](CreateSeriesIdentifierField.md) | Optional | The schema defining the structure and data types of the relational dataset. |
| **ValueAndMetadataFields** | [List&lt;RelationalDatasetFieldDefinition&gt;](RelationalDatasetFieldDefinition.md) | Optional | The schema defining the structure and data types of the relational dataset. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationalDatasetFieldsToAdd(
    seriesIdentifiers: new List<CreateSeriesIdentifierField>(),  // optional — The schema defining the structure and data types of the relational dataset.
    valueAndMetadataFields: new List<RelationalDatasetFieldDefinition>()  // optional — The schema defining the structure and data types of the relational dataset.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationalDatasetFieldsToAdd>(json);
```


## Related Models

- [CreateSeriesIdentifierField](CreateSeriesIdentifierField.md) — used in `SeriesIdentifiers`
- [RelationalDatasetFieldDefinition](RelationalDatasetFieldDefinition.md) — used in `ValueAndMetadataFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

