# Finbourne.Sdk.Lusid.Model.BondForwardModelOptions

Model options for bond forward pricing.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BondForwardProjectionType** | **string** | Optional | Determines how the forward price of the deliverable bond is projected to the settlement date.                Supported string (enumeration) values are: [QuotedContractPrice, ForwardProjectedFromFundingCurve,  DeliverableSpreadAnchoredToQuote].  Defaults to QuotedContractPrice - the original quote-driven behaviour - when not supplied, so  options persisted before this property existed keep the behaviour they were saved under.                ForwardProjectedFromFundingCurve carries the deliverable&#39;s quoted dirty spot to settlement on the  discount curve. DeliverableSpreadAnchoredToQuote does the same carry but models that spot as well,  off the spread anchored for the deliverable in the base market, which is what gives the forward  the deliverable&#39;s own curve delta rather than only the carry&#39;s - the larger of the two terms. It  requires the deliverable to be a mastered Bond or ComplexBond settling in the forward&#39;s own  currency, and a credit-spread curve or ZSpread quote to be resolvable for it. |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions, BondForwardModelOptions. Default: `ModelOptionsTypeEnum.BondForwardModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondForwardModelOptions(
    bondForwardProjectionType: "...",  // optional — Determines how the forward price of the deliverable bond is projected to the settlement date.                Supported string (enumeration) values are: [QuotedContractPrice, ForwardProjectedFromFundingCurve,  DeliverableSpreadAnchoredToQuote].  Defaults to QuotedContractPrice - the original quote-driven behaviour - when not supplied, so  options persisted before this property existed keep the behaviour they were saved under.                ForwardProjectedFromFundingCurve carries the deliverable&#39;s quoted dirty spot to settlement on the  discount curve. DeliverableSpreadAnchoredToQuote does the same carry but models that spot as well,  off the spread anchored for the deliverable in the base market, which is what gives the forward  the deliverable&#39;s own curve delta rather than only the carry&#39;s - the larger of the two terms. It  requires the deliverable to be a mastered Bond or ComplexBond settling in the forward&#39;s own  currency, and a credit-spread curve or ZSpread quote to be resolvable for it.
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions, BondForwardModelOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondForwardModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

