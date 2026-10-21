# Finbourne.Sdk.Lusid.Model.PopulateResultProperty

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Required | The property the formula populates. Must be an existing, single-valued property in the RecResult domain, and may appear only once. |
| **Formula** | **string** | Required | The formula whose value populates the property; a null value means the property has no value. |
| **OverwriteManualEditsOnReRun** | **bool?** | Optional | Whether a value edited since the property was last populated is replaced. Defaults to false, so manual edits are kept. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PopulateResultProperty(
    propertyKey: "...",  // required — The property the formula populates. Must be an existing, single-valued property in the RecResult domain, and may appear only once.
    formula: "...",  // required — The formula whose value populates the property; a null value means the property has no value.
    overwriteManualEditsOnReRun: true  // optional — Whether a value edited since the property was last populated is replaced. Defaults to false, so manual edits are kept.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PopulateResultProperty>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

