# Finbourne.Sdk.Lusid.Model.EmptyModelOptions

> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ModelOptionsType** | **string** | Required | The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions Default: `ModelOptionsTypeEnum.EmptyModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EmptyModelOptions(
    modelOptionsType: "..."  // required — The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EmptyModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

