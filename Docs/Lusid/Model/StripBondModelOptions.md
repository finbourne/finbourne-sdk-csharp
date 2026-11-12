# Finbourne.Sdk.Lusid.Model.StripBondModelOptions

Model options for StripBond pricing: how a strip's cash receipts are split between income and return of  capital. Set on the VendorModelRule for StripBond under the BondLookupPricer, SimpleStatic or  OverrideOnlyPricer model.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StripAccountingChoice** | **string** | Optional | How a StripBond&#39;s cash receipts are split between income and return of capital.  Null means CostRecovery: the effective yield is 0, every receipt returns capital until cost is recovered.  QuotedYield reads the strip&#39;s EffectiveYield quote at the parent flow&#39;s ex-date.  CashAsReceived applies no yield: each receipt is booked as the parent paid it, an interest-only strip&#39;s  cash as income and a principal-only strip&#39;s as return of capital.                Supported string (enumeration) values are: [CostRecovery, QuotedYield, CashAsReceived]. |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions, BondForwardModelOptions, SimpleModelOptions, StripBondModelOptions. Default: `ModelOptionsTypeEnum.StripBondModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StripBondModelOptions(
    stripAccountingChoice: "...",  // optional — How a StripBond&#39;s cash receipts are split between income and return of capital.  Null means CostRecovery: the effective yield is 0, every receipt returns capital until cost is recovered.  QuotedYield reads the strip&#39;s EffectiveYield quote at the parent flow&#39;s ex-date.  CashAsReceived applies no yield: each receipt is booked as the parent paid it, an interest-only strip&#39;s  cash as income and a principal-only strip&#39;s as return of capital.                Supported string (enumeration) values are: [CostRecovery, QuotedYield, CashAsReceived].
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions, BondForwardModelOptions, SimpleModelOptions, StripBondModelOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StripBondModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

