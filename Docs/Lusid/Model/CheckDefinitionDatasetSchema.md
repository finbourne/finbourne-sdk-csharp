# Finbourne.Sdk.Lusid.Model.CheckDefinitionDatasetSchema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of dataset schema that the Check Definition applies to |
| **EntityType** | **string** | Optional | The type of entity that the dataset schema applies to, e.g. Instrument, Transaction, etc. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CheckDefinitionDatasetSchema(
    type: "...",  // optional — The type of dataset schema that the Check Definition applies to
    entityType: "..."  // optional — The type of entity that the dataset schema applies to, e.g. Instrument, Transaction, etc.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CheckDefinitionDatasetSchema>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

