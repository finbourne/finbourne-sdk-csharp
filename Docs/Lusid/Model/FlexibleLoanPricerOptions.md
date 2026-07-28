# Finbourne.Sdk.Lusid.Model.FlexibleLoanPricerOptions

Model options for instruments of type flexibleDeposit and flexibleLoan when used on a standalone basis.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SetCleanPVToZero** | **bool** | Required | If set to true the CleanPV will be set to zero in valuations and PV will effectively just be the Accrual. |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions. Default: `ModelOptionsTypeEnum.FlexibleLoanPricerOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FlexibleLoanPricerOptions(
    setCleanPVToZero: true,  // required — If set to true the CleanPV will be set to zero in valuations and PV will effectively just be the Accrual.
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FlexibleLoanPricerOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

