# Finbourne.Sdk.Lusid.Model.ComplianceRunConfiguration

Specification object for the configuration parameters of a compliance run
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PreTradeConfiguration** | [PreTradeConfiguration](PreTradeConfiguration.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRunConfiguration(
    preTradeConfiguration: new PreTradeConfiguration(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRunConfiguration>(json);
```


## Related Models

- [PreTradeConfiguration](PreTradeConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

