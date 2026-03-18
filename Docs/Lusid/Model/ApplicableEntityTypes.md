# Finbourne.Sdk.Lusid.Model.ApplicableEntityTypes

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApplicableEntityTypesToAdd** | **List&lt;string&gt;** | Optional | The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.). |
| **ApplicableEntityTypesToRemove** | **List&lt;string&gt;** | Optional | The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ApplicableEntityTypes(
    applicableEntityTypesToAdd: ,  // optional — The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.).
    applicableEntityTypesToRemove:   // optional — The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApplicableEntityTypes>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

