# Finbourne.Sdk.Lusid.Model.DealingFlowSummary

The transfer agency estimates a swing decision was made on: the orders dealt at the valuation point, what they summed, and how many pending orders were left out and what those were worth.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Count** | **int** | Required | How many orders were summed. |
| **GrossInflow** | **decimal** | Required | The sum of the inflows, in the fund currency. Zero or more. |
| **GrossOutflow** | **decimal** | Required | The sum of the outflows, in the fund currency, as a magnitude. Zero or more. |
| **PendingNotCounted** | **int** | Required | How many pending orders at the valuation point were left out of the sums because the fund&#39;s dealing estimates do not count pending orders. Zero when the fund counts them. |
| **PendingGrossInflow** | **decimal** | Required | The sum of the inflows among the pending orders left out, in the fund currency, with units at the estimate price. Zero or more; zero when the fund counts pending orders. |
| **PendingGrossOutflow** | **decimal** | Required | The sum of the outflows among the pending orders left out, in the fund currency, as a magnitude, with units at the estimate price. Zero or more; zero when the fund counts pending orders. |
| **PendingUnvaluedCount** | **int** | Required | How many of the pending orders left out could not be valued, such as a unit order with no price yet. They are in pendingNotCounted but absent from pendingGrossInflow and pendingGrossOutflow. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DealingFlowSummary(
    count: 0,  // required — How many orders were summed.
    grossInflow: 0.0d,  // required — The sum of the inflows, in the fund currency. Zero or more.
    grossOutflow: 0.0d,  // required — The sum of the outflows, in the fund currency, as a magnitude. Zero or more.
    pendingNotCounted: 0,  // required — How many pending orders at the valuation point were left out of the sums because the fund&#39;s dealing estimates do not count pending orders. Zero when the fund counts them.
    pendingGrossInflow: 0.0d,  // required — The sum of the inflows among the pending orders left out, in the fund currency, with units at the estimate price. Zero or more; zero when the fund counts pending orders.
    pendingGrossOutflow: 0.0d,  // required — The sum of the outflows among the pending orders left out, in the fund currency, as a magnitude, with units at the estimate price. Zero or more; zero when the fund counts pending orders.
    pendingUnvaluedCount: 0  // required — How many of the pending orders left out could not be valued, such as a unit order with no price yet. They are in pendingNotCounted but absent from pendingGrossInflow and pendingGrossOutflow.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DealingFlowSummary>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

