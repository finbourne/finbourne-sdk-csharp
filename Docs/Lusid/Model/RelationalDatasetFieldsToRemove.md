# Finbourne.Sdk.Lusid.Model.RelationalDatasetFieldsToRemove

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ValueAndMetadataFields** | **List&lt;string&gt;** | Optional | An array of FieldName(s) to be removed from the FieldSchema. Only Value or Metadata fields can be removed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationalDatasetFieldsToRemove(
    valueAndMetadataFields:   // optional — An array of FieldName(s) to be removed from the FieldSchema. Only Value or Metadata fields can be removed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationalDatasetFieldsToRemove>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

