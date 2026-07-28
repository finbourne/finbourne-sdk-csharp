# Finbourne.Sdk.Lusid.Model.FxForwardModelOptions

> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ForwardRateObservableType** | **string** | Required | Available values: ForwardPoints, ForwardRate, RatesCurve, FxForwardCurve, Invalid. |
| **DiscountingMethod** | **string** | Required | Available values: Standard, ConstantTimeValueOfMoney, Invalid. |
| **ConvertToReportCcy** | **bool** | Required | Convert all FX flows to the report currency  By setting this all FX forwards will be priced using Forward Curves that have Report Currency as the base. |
| **AllowSpotFallbackForReportCcy** | **bool** | Optional | When converting to the report currency, allow falling back to pricing off the natural-pair forward  and converting to the report currency at spot when the report-currency cross forward curves are not  available. Defaults to false, in which case the report-currency cross forwards are required. |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions. Default: `ModelOptionsTypeEnum.FxForwardModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForwardModelOptions(
    forwardRateObservableType: "...",  // required — Available values: ForwardPoints, ForwardRate, RatesCurve, FxForwardCurve, Invalid.
    discountingMethod: "...",  // required — Available values: Standard, ConstantTimeValueOfMoney, Invalid.
    convertToReportCcy: true,  // required — Convert all FX flows to the report currency  By setting this all FX forwards will be priced using Forward Curves that have Report Currency as the base.
    allowSpotFallbackForReportCcy: true,  // optional — When converting to the report currency, allow falling back to pricing off the natural-pair forward  and converting to the report currency at spot when the report-currency cross forward curves are not  available. Defaults to false, in which case the report-currency cross forwards are required.
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxForwardModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

