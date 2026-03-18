# Finbourne.Sdk.Lusid.Model.OrderGraphPlacement

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Placement** | [Placement](Placement.md) | Required | *No description available.* |
| **BlockId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Ordered** | [OrderGraphPlacementOrderSynopsis](OrderGraphPlacementOrderSynopsis.md) | Required | *No description available.* |
| **Placed** | [OrderGraphPlacementPlacementSynopsis](OrderGraphPlacementPlacementSynopsis.md) | Required | *No description available.* |
| **Executed** | [OrderGraphPlacementExecutionSynopsis](OrderGraphPlacementExecutionSynopsis.md) | Required | *No description available.* |
| **Allocated** | [OrderGraphPlacementAllocationSynopsis](OrderGraphPlacementAllocationSynopsis.md) | Required | *No description available.* |
| **DerivedState** | **string** | Required | A simple description of the overall state of a placement. |
| **CalculatedAveragePrice** | **decimal?** | Optional | Average price realised on executions for a given placement |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphPlacement(
    placement: new Placement(...),  // required
    blockId: new ResourceId(...),  // required
    ordered: new OrderGraphPlacementOrderSynopsis(...),  // required
    placed: new OrderGraphPlacementPlacementSynopsis(...),  // required
    executed: new OrderGraphPlacementExecutionSynopsis(...),  // required
    allocated: new OrderGraphPlacementAllocationSynopsis(...),  // required
    derivedState: "...",  // required — A simple description of the overall state of a placement.
    calculatedAveragePrice: 0.0d  // optional — Average price realised on executions for a given placement
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphPlacement>(json);
```


## Related Models

- [Placement](Placement.md)
- [ResourceId](ResourceId.md)
- [OrderGraphPlacementOrderSynopsis](OrderGraphPlacementOrderSynopsis.md)
- [OrderGraphPlacementPlacementSynopsis](OrderGraphPlacementPlacementSynopsis.md)
- [OrderGraphPlacementExecutionSynopsis](OrderGraphPlacementExecutionSynopsis.md)
- [OrderGraphPlacementAllocationSynopsis](OrderGraphPlacementAllocationSynopsis.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

