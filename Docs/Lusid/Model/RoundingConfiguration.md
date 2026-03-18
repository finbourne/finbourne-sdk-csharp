# Finbourne.Sdk.Lusid.Model.RoundingConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StockUnits** | [RoundingConfigurationComponent](RoundingConfigurationComponent.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RoundingConfiguration(
    stockUnits: new RoundingConfigurationComponent(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RoundingConfiguration>(json);
```


## Related Models

- [RoundingConfigurationComponent](RoundingConfigurationComponent.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

