# Finbourne.Sdk.Lusid.Model.SwingPricingDecision

Deprecated and no longer produced; see the share class's pricing methodology result.  What the NAV type's swing pricing rule decided for a valuation point: the net dealing flow it measured, how  it compared with the threshold, and the pricing basis the point was valued on as a result.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NetDealingFlow** | **decimal** | Optional | The net dealing flow the rule measured for the valuation point, in the fund currency. Subscriptions are positive and redemptions negative. |
| **NetDealingFlowPercentageOfNav** | **decimal** | Optional | The net dealing flow as a percentage of the previous valuation point&#39;s NAV. Zero when there is no previous NAV to measure against. |
| **ThresholdPercentageOfNav** | **decimal** | Optional | The threshold the rule compared the flow with. |
| **Direction** | **string** | Optional | Whether the fund swung and which way: None, Inflow or Outflow. |
| **PricingBasisApplied** | **string** | Optional | The pricing basis the valuation point was valued on after the rule was applied. Absent when the fund did not swing and the NAV type defers to the recipe. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingPricingDecision(
    netDealingFlow: 0.0d,  // optional — The net dealing flow the rule measured for the valuation point, in the fund currency. Subscriptions are positive and redemptions negative.
    netDealingFlowPercentageOfNav: 0.0d,  // optional — The net dealing flow as a percentage of the previous valuation point&#39;s NAV. Zero when there is no previous NAV to measure against.
    thresholdPercentageOfNav: 0.0d,  // optional — The threshold the rule compared the flow with.
    direction: "...",  // optional — Whether the fund swung and which way: None, Inflow or Outflow.
    pricingBasisApplied: "..."  // optional — The pricing basis the valuation point was valued on after the rule was applied. Absent when the fund did not swing and the NAV type defers to the recipe.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingPricingDecision>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

