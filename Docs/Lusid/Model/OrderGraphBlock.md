# Finbourne.Sdk.Lusid.Model.OrderGraphBlock

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Block** | [Block](Block.md) | Required | *No description available.* |
| **Ordered** | [OrderGraphBlockOrderSynopsis](OrderGraphBlockOrderSynopsis.md) | Required | *No description available.* |
| **Placed** | [OrderGraphBlockPlacementSynopsis](OrderGraphBlockPlacementSynopsis.md) | Required | *No description available.* |
| **Executed** | [OrderGraphBlockExecutionSynopsis](OrderGraphBlockExecutionSynopsis.md) | Required | *No description available.* |
| **Allocated** | [OrderGraphBlockAllocationSynopsis](OrderGraphBlockAllocationSynopsis.md) | Required | *No description available.* |
| **Booked** | [OrderGraphBlockTransactionSynopsis](OrderGraphBlockTransactionSynopsis.md) | Required | *No description available.* |
| **DerivedState** | **string** | Required | A simple description of the overall state of a block. |
| **DerivedComplianceState** | **string** | Required | The overall compliance state of a block, derived from the block&#39;s orders. Possible values are &#39;Pending&#39;, &#39;Failed&#39;, &#39;Manually approved&#39; and &#39;Passed&#39;. |
| **DerivedApprovalState** | **string** | Required | The overall approval state of a block, derived from approval of the block&#39;s orders. Possible values are &#39;Pending&#39;, &#39;Approved&#39; and &#39;Rejected&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlock(
    block: new Block(...),  // required
    ordered: new OrderGraphBlockOrderSynopsis(...),  // required
    placed: new OrderGraphBlockPlacementSynopsis(...),  // required
    executed: new OrderGraphBlockExecutionSynopsis(...),  // required
    allocated: new OrderGraphBlockAllocationSynopsis(...),  // required
    booked: new OrderGraphBlockTransactionSynopsis(...),  // required
    derivedState: "...",  // required — A simple description of the overall state of a block.
    derivedComplianceState: "...",  // required — The overall compliance state of a block, derived from the block&#39;s orders. Possible values are &#39;Pending&#39;, &#39;Failed&#39;, &#39;Manually approved&#39; and &#39;Passed&#39;.
    derivedApprovalState: "..."  // required — The overall approval state of a block, derived from approval of the block&#39;s orders. Possible values are &#39;Pending&#39;, &#39;Approved&#39; and &#39;Rejected&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlock>(json);
```


## Related Models

- [Block](Block.md)
- [OrderGraphBlockOrderSynopsis](OrderGraphBlockOrderSynopsis.md)
- [OrderGraphBlockPlacementSynopsis](OrderGraphBlockPlacementSynopsis.md)
- [OrderGraphBlockExecutionSynopsis](OrderGraphBlockExecutionSynopsis.md)
- [OrderGraphBlockAllocationSynopsis](OrderGraphBlockAllocationSynopsis.md)
- [OrderGraphBlockTransactionSynopsis](OrderGraphBlockTransactionSynopsis.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

