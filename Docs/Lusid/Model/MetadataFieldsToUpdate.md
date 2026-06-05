# Finbourne.Sdk.Lusid.Model.MetadataFieldsToUpdate

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MetadataFields** | [List&lt;MetadataFieldDefinition&gt;](MetadataFieldDefinition.md) | Optional | The metadata field definitions for this configuration. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MetadataFieldsToUpdate(
    metadataFields: new List<MetadataFieldDefinition>()  // optional — The metadata field definitions for this configuration.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetadataFieldsToUpdate>(json);
```


## Related Models

- [MetadataFieldDefinition](MetadataFieldDefinition.md) — used in `MetadataFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

