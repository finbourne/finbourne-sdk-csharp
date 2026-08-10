# Finbourne.Sdk.Lusid.Model.CashFlowHaircutRule

A rule describing how projected cashflow inflows are reduced by a haircut representing expected  default loss or cost of downgrade, for matching-adjustment and liquidity (Solvency II) analyses.  Rules are matched in request order against each cashflow's instrument and the first matching rule  wins; a rule with no criteria acts as a catch-all. Only inflows are haircut; outflows always pass  through untouched.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Optional | Optional identifier reported back against cashflows this rule haircut. Defaults to the rule&#39;s position in the list, e.g. &#39;HaircutRules[0]&#39;. |
| **PropertyKey** | **string** | Optional | The instrument property key the rule matches on, e.g. &#39;Instrument/default/CreditRating&#39;. When omitted the rule does not match on a property. |
| **PropertyValue** | **string** | Optional | The instrument property value the rule matches. Required when PropertyKey is supplied. |
| **InstrumentType** | **string** | Optional | Optional instrument type filter, e.g. &#39;Bond&#39;. When supplied the rule only matches cashflows from instruments of that type. |
| **HaircutType** | **string** | Required | The mathematical form of the haircut. One of &#39;CumulativeAnnualised&#39; (net &#x3D; gross x (1 - rate)^t, where t is the ACT/365.25 year fraction from the valuation date to the payment date) or &#39;Flat&#39; (net &#x3D; gross x (1 - h(t)), where h(t) is the flat rate or the term structure rate at t). Available values: CumulativeAnnualised, Flat. |
| **Rate** | **decimal?** | Optional | The haircut rate as a fraction in the range [0, 1]. Exactly one of Rate and TermStructure must be supplied. |
| **TermStructure** | [List&lt;CashFlowHaircutTermPoint&gt;](CashFlowHaircutTermPoint.md) | Optional | The haircut rate term structure, linearly interpolated on time-to-payment with flat extrapolation beyond either end. Exactly one of Rate and TermStructure must be supplied. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashFlowHaircutRule(
    ruleId: "...",  // optional — Optional identifier reported back against cashflows this rule haircut. Defaults to the rule&#39;s position in the list, e.g. &#39;HaircutRules[0]&#39;.
    propertyKey: "...",  // optional — The instrument property key the rule matches on, e.g. &#39;Instrument/default/CreditRating&#39;. When omitted the rule does not match on a property.
    propertyValue: "...",  // optional — The instrument property value the rule matches. Required when PropertyKey is supplied.
    instrumentType: "...",  // optional — Optional instrument type filter, e.g. &#39;Bond&#39;. When supplied the rule only matches cashflows from instruments of that type.
    haircutType: "...",  // required — The mathematical form of the haircut. One of &#39;CumulativeAnnualised&#39; (net &#x3D; gross x (1 - rate)^t, where t is the ACT/365.25 year fraction from the valuation date to the payment date) or &#39;Flat&#39; (net &#x3D; gross x (1 - h(t)), where h(t) is the flat rate or the term structure rate at t). Available values: CumulativeAnnualised, Flat.
    rate: 0.0d,  // optional — The haircut rate as a fraction in the range [0, 1]. Exactly one of Rate and TermStructure must be supplied.
    termStructure: new List<CashFlowHaircutTermPoint>()  // optional — The haircut rate term structure, linearly interpolated on time-to-payment with flat extrapolation beyond either end. Exactly one of Rate and TermStructure must be supplied.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashFlowHaircutRule>(json);
```

- [CashFlowHaircutTermPoint](CashFlowHaircutTermPoint.md) — used in `TermStructure`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

