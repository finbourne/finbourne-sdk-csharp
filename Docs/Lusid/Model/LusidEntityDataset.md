# Finbourne.Sdk.Lusid.Model.LusidEntityDataset

Contains the run-time parameters that are appropriate for check definitions  with datasetSchema.type = \"LusidEntity\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The asAt date to fetch the data. Nullable. Defaults to latest. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effectiveAt date to fetch the data. Nullable. Defaults to latest. |
| **Scope** | **string** | Optional | The scope of the entities to check. Required. |
| **AsAtModifiedSince** | **DateTimeOffset?** | Optional | Nullable. Filters the dataset for version.asAtModified greater than or equal to this value. |
| **SelectorAttribute** | **string** | Optional | An attribute (field name, propertyKey or identifierKey) to use to sub-divide the dataset. |
| **SelectorValue** | **string** | Optional | The value of the above attribute used to sub-divide the dataset. |
| **ReturnIdentifierKey** | **string** | Optional | The preferred identifier to return for entities with multiple external identifiers. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LusidEntityDataset(
    asAt: DateTimeOffset.Now,  // optional — The asAt date to fetch the data. Nullable. Defaults to latest.
    effectiveAt: DateTimeOffset.Now,  // optional — The effectiveAt date to fetch the data. Nullable. Defaults to latest.
    scope: "...",  // optional — The scope of the entities to check. Required.
    asAtModifiedSince: DateTimeOffset.Now,  // optional — Nullable. Filters the dataset for version.asAtModified greater than or equal to this value.
    selectorAttribute: "...",  // optional — An attribute (field name, propertyKey or identifierKey) to use to sub-divide the dataset.
    selectorValue: "...",  // optional — The value of the above attribute used to sub-divide the dataset.
    returnIdentifierKey: "..."  // optional — The preferred identifier to return for entities with multiple external identifiers.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidEntityDataset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

