# Finbourne.Sdk.Lusid.Model.SwingPricingRule

Deprecated and ignored; use the Fund's pricing methodology.  Moved a NAV type's pricing basis with its net dealing flow. When the flow, as a percentage of the previous  valuation point's NAV, exceeded the threshold the fund was valued on the inflow or outflow basis instead of  the NAV type's own basis.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ThresholdPercentageOfNav** | **decimal** | Required | The net dealing flow, as a percentage of the previous valuation point&#39;s NAV, above which the fund swings. Must be zero or more; zero swings on any non-zero flow. |
| **InflowBasis** | **string** | Optional | The pricing basis the fund is valued on when net subscriptions exceed the threshold: Mid, Bid or Ask. Defaults to Ask. Available values: Mid, Bid, Ask. |
| **OutflowBasis** | **string** | Optional | The pricing basis the fund is valued on when net redemptions exceed the threshold: Mid, Bid or Ask. Defaults to Bid. Available values: Mid, Bid, Ask. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingPricingRule(
    thresholdPercentageOfNav: 0.0d,  // required — The net dealing flow, as a percentage of the previous valuation point&#39;s NAV, above which the fund swings. Must be zero or more; zero swings on any non-zero flow.
    inflowBasis: "...",  // optional — The pricing basis the fund is valued on when net subscriptions exceed the threshold: Mid, Bid or Ask. Defaults to Ask. Available values: Mid, Bid, Ask.
    outflowBasis: "..."  // optional — The pricing basis the fund is valued on when net redemptions exceed the threshold: Mid, Bid or Ask. Defaults to Bid. Available values: Mid, Bid, Ask.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingPricingRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

