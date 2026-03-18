# Finbourne.Sdk.Lusid.Model.RelationalDataSeriesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesScope** | **string** | Required | The scope of the DataSeries. |
| **ApplicableEntity** | [ApplicableEntity](ApplicableEntity.md) | Required | *No description available.* |
| **SeriesIdentifiers** | [Dictionary&lt;string, RelationalDataPointFieldValueResponse&gt;](RelationalDataPointFieldValueResponse.md) | Required | The identifiers that uniquely define this DataSeries, if any, structured according to the FieldSchema of the parent RelationalDatasetDefinition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationalDataSeriesResponse(
    seriesScope: "...",  // required — The scope of the DataSeries.
    applicableEntity: new ApplicableEntity(...),  // required
    seriesIdentifiers: new RelationalDataPointFieldValueResponse(...)  // required — The identifiers that uniquely define this DataSeries, if any, structured according to the FieldSchema of the parent RelationalDatasetDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationalDataSeriesResponse>(json);
```

- [ApplicableEntity](ApplicableEntity.md)
- [RelationalDataPointFieldValueResponse](RelationalDataPointFieldValueResponse.md) — used in `SeriesIdentifiers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

