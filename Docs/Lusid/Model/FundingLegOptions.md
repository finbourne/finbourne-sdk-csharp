# Finbourne.Sdk.Lusid.Model.FundingLegOptions

> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ModelOptionsType** | **string** | Required | The available values are: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions *(inherited)* |
| **ExpectedFundingLegNotional** | **string** | Required | Assumption made on future expected notional of the funding leg. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundingLegOptions(
    expectedFundingLegNotional: "..."  // required — Assumption made on future expected notional of the funding leg.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundingLegOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

