# Finbourne.Sdk.Lusid.Model.CustomDataModel

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DataModelSummary** | [DataModelSummary](DataModelSummary.md) | Optional | *No description available.* |
| **Inherited** | [CustomDataModelCriteria](CustomDataModelCriteria.md) | Optional | *No description available.* |
| **Incremental** | [CustomDataModelCriteria](CustomDataModelCriteria.md) | Optional | *No description available.* |
| **Applied** | [CustomDataModelCriteria](CustomDataModelCriteria.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomDataModel(
    dataModelSummary: new DataModelSummary(...),  // optional
    inherited: new CustomDataModelCriteria(...),  // optional
    incremental: new CustomDataModelCriteria(...),  // optional
    applied: new CustomDataModelCriteria(...),  // optional
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomDataModel>(json);
```


## Related Models

- [DataModelSummary](DataModelSummary.md)
- [CustomDataModelCriteria](CustomDataModelCriteria.md)
- [CustomDataModelCriteria](CustomDataModelCriteria.md)
- [CustomDataModelCriteria](CustomDataModelCriteria.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

