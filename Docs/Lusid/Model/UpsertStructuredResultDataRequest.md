# Finbourne.Sdk.Lusid.Model.UpsertStructuredResultDataRequest

The details of the structured unit result data item to upsert into Lusid.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [StructuredResultDataId](StructuredResultDataId.md) | Required | *No description available.* |
| **Data** | [StructuredResultData](StructuredResultData.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertStructuredResultDataRequest(
    id: new StructuredResultDataId(...),  // required
    data: new StructuredResultData(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertStructuredResultDataRequest>(json);
```


## Related Models

- [StructuredResultDataId](StructuredResultDataId.md)
- [StructuredResultData](StructuredResultData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

