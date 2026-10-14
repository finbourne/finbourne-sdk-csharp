# Finbourne.Sdk.Lusid.Model.PricingMethodologyAudit

The working behind a share class's dealing price: the net cashflow it was decided on, the spread applied and  what the methodology alone proposed, with how any Market swing triggers were evaluated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NetCashflow** | **decimal** | Required | The fund&#39;s net dealing cashflow for the valuation point, in the fund currency. An inflow is positive and an outflow negative. |
| **NetCashflowPctOfNav** | **decimal?** | Optional | The net cashflow as a percentage of the previous valuation point&#39;s NAV. Absent when there is no previous NAV to measure it against. |
| **SpreadsApplied** | [SwingSpreadApplied](SwingSpreadApplied.md) | Optional | *No description available.* |
| **EngineProposal** | [PricingMethodologyEngineProposal](PricingMethodologyEngineProposal.md) | Required | *No description available.* |
| **Override** | [PricingMethodologyOverride](PricingMethodologyOverride.md) | Optional | *No description available.* |
| **InflowTrigger** | [SwingTriggerEvaluation](SwingTriggerEvaluation.md) | Optional | *No description available.* |
| **OutflowTrigger** | [SwingTriggerEvaluation](SwingTriggerEvaluation.md) | Optional | *No description available.* |
| **DealingFlows** | [DealingFlowSummary](DealingFlowSummary.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingMethodologyAudit(
    netCashflow: 0.0d,  // required — The fund&#39;s net dealing cashflow for the valuation point, in the fund currency. An inflow is positive and an outflow negative.
    netCashflowPctOfNav: 0.0d,  // optional — The net cashflow as a percentage of the previous valuation point&#39;s NAV. Absent when there is no previous NAV to measure it against.
    spreadsApplied: new SwingSpreadApplied(...),  // optional
    engineProposal: new PricingMethodologyEngineProposal(...),  // required
    varOverride: new PricingMethodologyOverride(...),  // optional
    inflowTrigger: new SwingTriggerEvaluation(...),  // optional
    outflowTrigger: new SwingTriggerEvaluation(...),  // optional
    dealingFlows: new DealingFlowSummary(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingMethodologyAudit>(json);
```

- [SwingSpreadApplied](SwingSpreadApplied.md)
- [PricingMethodologyEngineProposal](PricingMethodologyEngineProposal.md)
- [PricingMethodologyOverride](PricingMethodologyOverride.md)
- [SwingTriggerEvaluation](SwingTriggerEvaluation.md)
- [SwingTriggerEvaluation](SwingTriggerEvaluation.md)
- [DealingFlowSummary](DealingFlowSummary.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

