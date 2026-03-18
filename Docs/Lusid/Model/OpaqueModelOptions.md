# Finbourne.Sdk.Lusid.Model.OpaqueModelOptions

> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Data** | **Dictionary&lt;string, Object&gt;** | Required | *No description available.* |
| **ModelOptionsType** | **string** | Required | The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions Default: `ModelOptionsTypeEnum.OpaqueModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OpaqueModelOptions(
    data: ,  // required
    modelOptionsType: "..."  // required — The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OpaqueModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

