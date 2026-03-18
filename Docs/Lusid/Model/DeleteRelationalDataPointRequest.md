# Finbourne.Sdk.Lusid.Model.DeleteRelationalDataPointRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataSeries** | [DataSeries](DataSeries.md) | Required | *No description available.* |
| **EffectiveAt** | **string** | Required | The effectiveAt or cut-label datetime of the DataPoint. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteRelationalDataPointRequest(
    dataSeries: new DataSeries(...),  // required
    effectiveAt: "..."  // required — The effectiveAt or cut-label datetime of the DataPoint.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteRelationalDataPointRequest>(json);
```


## Related Models

- [DataSeries](DataSeries.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

