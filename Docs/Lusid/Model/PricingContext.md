# Finbourne.Sdk.Lusid.Model.PricingContext

Pricing context node. In order to price an instrument a number of configuration parameters are required to determine which  (a) pricing model (ranging from a simple lookup of a market quote/price through to a Monte-Carlo simulation for the behaviour of its cashflows)  (b) vendor library (Lusid internal models or those provided through an external Vendor such as Refinitiv (proprietary) or QuantLib (open source)  are used in the pricing.    In conjunction with these there are a number of parameters that govern the behaviour of these models. For example, in pricing an Fx volatility  dependent product such as an Fx option, there are various parameters that affect model behaviour for the smile. In Lusid a distinction is made between  those which are understood natively and those which are only held for use with a given vendor-model combination. The problem is that, unlike market  quote data, there are few standards around model descriptions. Hence, apparently similar terminology can be mis-leading; for example in SABR models where  the basic parameters are agreed upon but most practical models have used an approximation with adjustments where the parameters can have wildly different meanings.  To avoid confusion or mis-behaviour in this area, where parameters are not understood to be interchangeable, they are only settable on a per-library per-model  basis, essentially as opaque data that will be given to the Vendor library \"verbatim\" but not used with any other.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ModelRules** | [List&lt;VendorModelRule&gt;](VendorModelRule.md) | Optional | The set of model rules that are available. There may be multiple rules for Vendors, but only one per model-instrument pair.  Which of these preference sets is used depends upon the model choice selection if specified, or failing that the global default model specification  in the options. |
| **ModelChoice** | [Dictionary&lt;string, ModelSelection&gt;](ModelSelection.md) | Optional | The choice of which model selection (vendor library, pricing model) to use in evaluation of a given instrument type. |
| **Options** | [PricingOptions](PricingOptions.md) | Optional | *No description available.* |
| **ResultDataRules** | [List&lt;ResultKeyRule&gt;](ResultKeyRule.md) | Optional | Set of rules that control querying of unit results either for direct queries into aggregation or for  overriding intermediate calculations. For example, a dirty price is made up from a clean price and the accrued interest.  One might consider overriding the accrued interest calculated by a model (perhaps one wants to match an external value or simply disagrees with the  calculated result) and use that in calculation of the dirty price. |
| **HoldingPricingInfo** | [HoldingPricingInfo](HoldingPricingInfo.md) | Optional | *No description available.* |
| **AccrualDefinition** | **string** | Optional | Determines which method to use for the calculation of accrued interest. Defaults to SOD. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingContext(
    modelRules: new List<VendorModelRule>(),  // optional — The set of model rules that are available. There may be multiple rules for Vendors, but only one per model-instrument pair.  Which of these preference sets is used depends upon the model choice selection if specified, or failing that the global default model specification  in the options.
    modelChoice: new ModelSelection(...),  // optional — The choice of which model selection (vendor library, pricing model) to use in evaluation of a given instrument type.
    options: new PricingOptions(...),  // optional
    resultDataRules: new List<ResultKeyRule>(),  // optional — Set of rules that control querying of unit results either for direct queries into aggregation or for  overriding intermediate calculations. For example, a dirty price is made up from a clean price and the accrued interest.  One might consider overriding the accrued interest calculated by a model (perhaps one wants to match an external value or simply disagrees with the  calculated result) and use that in calculation of the dirty price.
    holdingPricingInfo: new HoldingPricingInfo(...),  // optional
    accrualDefinition: "..."  // optional — Determines which method to use for the calculation of accrued interest. Defaults to SOD.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingContext>(json);
```


## Related Models

- [VendorModelRule](VendorModelRule.md) — used in `ModelRules`
- [ModelSelection](ModelSelection.md) — used in `ModelChoice`
- [PricingOptions](PricingOptions.md)
- [ResultKeyRule](ResultKeyRule.md) — used in `ResultDataRules`
- [HoldingPricingInfo](HoldingPricingInfo.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

