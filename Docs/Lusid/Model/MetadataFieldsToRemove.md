# Finbourne.Sdk.Lusid.Model.MetadataFieldsToRemove

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MetadataFields** | **List&lt;string&gt;** | Optional | An array of FieldName(s) to be removed from the metadata field schema. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MetadataFieldsToRemove(
    metadataFields:   // optional — An array of FieldName(s) to be removed from the metadata field schema.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetadataFieldsToRemove>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

