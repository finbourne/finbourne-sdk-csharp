# Finbourne.Sdk.Lusid.Model.HoldingPropertyDelta

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingPropertyKey** | **string** | Required | The running balance on the holding to adjust. Allowed values: &#39;CommittedCapital&#39;, &#39;FundedCapital&#39;, &#39;UnfundedCapital&#39;, &#39;RecallableCapital&#39; and &#39;NonRecallableCapital&#39;. Available values: CommittedCapital, FundedCapital, UnfundedCapital, RecallableCapital, NonRecallableCapital. |
| **Source** | **string** | Required | The movement value that sources the adjustment. Allowed values: &#39;Amount&#39; (the movement&#39;s signed amount in transaction currency), &#39;Units&#39; (the movement&#39;s signed units) and &#39;PortfolioAmount&#39; (the movement&#39;s signed amount converted to portfolio currency). Available values: Amount, Units, PortfolioAmount. |
| **Direction** | **string** | Required | Whether the sourced value increases or decreases the balance. Allowed values: &#39;Increase&#39; and &#39;Decrease&#39;. Available values: Increase, Decrease. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingPropertyDelta(
    holdingPropertyKey: "...",  // required — The running balance on the holding to adjust. Allowed values: &#39;CommittedCapital&#39;, &#39;FundedCapital&#39;, &#39;UnfundedCapital&#39;, &#39;RecallableCapital&#39; and &#39;NonRecallableCapital&#39;. Available values: CommittedCapital, FundedCapital, UnfundedCapital, RecallableCapital, NonRecallableCapital.
    source: "...",  // required — The movement value that sources the adjustment. Allowed values: &#39;Amount&#39; (the movement&#39;s signed amount in transaction currency), &#39;Units&#39; (the movement&#39;s signed units) and &#39;PortfolioAmount&#39; (the movement&#39;s signed amount converted to portfolio currency). Available values: Amount, Units, PortfolioAmount.
    direction: "..."  // required — Whether the sourced value increases or decreases the balance. Allowed values: &#39;Increase&#39; and &#39;Decrease&#39;. Available values: Increase, Decrease.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingPropertyDelta>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

