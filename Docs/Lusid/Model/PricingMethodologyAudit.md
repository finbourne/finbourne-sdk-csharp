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
| **EstimateValuation** | [EstimateValuation](EstimateValuation.md) | Optional | *No description available.* |
| **ApprovalStatus** | **string** | Optional | Where a manually approved swing decision stands. Pending until a manager approves or overrides the engine&#39;s proposal, or when the proposal has changed since the decision was taken; Approved when the decision equals the proposal; Overridden when it differs. Absent when the swing policy approves automatically. |
| **DealingLinesNotValued** | [List&lt;DealingLineNotValued&gt;](DealingLineNotValued.md) | Optional | The dealing lines read for the swing decision that could not be valued into the share class currency: an amount in a currency that is neither the fund&#39;s nor any share class&#39;s, or a weight-only line. While any are present and no pricingMethodologyOverride has been submitted, no swing decision is taken, the dealing price is absent and the valuation point cannot be finalised; under an override the override&#39;s price stands and the lines remain listed here. Absent when every line was valued or the methodology does not swing. |
| **Completeness** | [DealingBookCompleteness](DealingBookCompleteness.md) | Optional | *No description available.* |


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
    dealingFlows: new DealingFlowSummary(...),  // optional
    estimateValuation: new EstimateValuation(...),  // optional
    approvalStatus: "...",  // optional — Where a manually approved swing decision stands. Pending until a manager approves or overrides the engine&#39;s proposal, or when the proposal has changed since the decision was taken; Approved when the decision equals the proposal; Overridden when it differs. Absent when the swing policy approves automatically.
    dealingLinesNotValued: new List<DealingLineNotValued>(),  // optional — The dealing lines read for the swing decision that could not be valued into the share class currency: an amount in a currency that is neither the fund&#39;s nor any share class&#39;s, or a weight-only line. While any are present and no pricingMethodologyOverride has been submitted, no swing decision is taken, the dealing price is absent and the valuation point cannot be finalised; under an override the override&#39;s price stands and the lines remain listed here. Absent when every line was valued or the methodology does not swing.
    completeness: new DealingBookCompleteness(...)  // optional
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
- [EstimateValuation](EstimateValuation.md)
- [DealingLineNotValued](DealingLineNotValued.md) — used in `DealingLinesNotValued`
- [DealingBookCompleteness](DealingBookCompleteness.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

