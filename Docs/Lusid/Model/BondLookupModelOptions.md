# Finbourne.Sdk.Lusid.Model.BondLookupModelOptions

Model options for the quote-anchored bond lookup pricer.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SpreadAnchoredRisk** | **bool** | Required | Price the bond by discounting its own cashflows over its discounting curve at a constant  spread, instead of marking it to its quoted price. Marking to a quote declares no curve  dependency, so a lookup-priced bond reports no curve delta at all. In this mode the pricer  declares both the discounting curve and a ZSpread quote for the instrument and prices off  them, so holding the spread fixed while the curve is perturbed produces the curve&#39;s delta.  Off by default, as the mode changes both the declared dependencies and where the price  comes from. |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions. Default: `ModelOptionsTypeEnum.BondLookupModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondLookupModelOptions(
    spreadAnchoredRisk: true,  // required — Price the bond by discounting its own cashflows over its discounting curve at a constant  spread, instead of marking it to its quoted price. Marking to a quote declares no curve  dependency, so a lookup-priced bond reports no curve delta at all. In this mode the pricer  declares both the discounting curve and a ZSpread quote for the instrument and prices off  them, so holding the spread fixed while the curve is perturbed produces the curve&#39;s delta.  Off by default, as the mode changes both the declared dependencies and where the price  comes from.
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondLookupModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

