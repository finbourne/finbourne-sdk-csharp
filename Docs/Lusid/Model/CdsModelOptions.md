# Finbourne.Sdk.Lusid.Model.CdsModelOptions

Model options for credit default instrument.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UseFactorsForCurrentNotional** | **bool** | Required | Determines if calculations that use current notional apply use a constituent weight factor from a quote representing a default. |
| **ModelOptionsType** | **string** | Required | The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions Default: `ModelOptionsTypeEnum.CdsModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CdsModelOptions(
    useFactorsForCurrentNotional: true,  // required — Determines if calculations that use current notional apply use a constituent weight factor from a quote representing a default.
    modelOptionsType: "..."  // required — The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CdsModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

