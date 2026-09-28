# Finbourne.Sdk.Lusid.Model.FundStructureNode

A node in a Fund Structure, representing a Fund and its role within the structure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NodeCode** | **string** | Required | A unique identifier for this node within the Fund Structure. |
| **FundScope** | **string** | Required | The scope of the Fund referenced by this node. |
| **FundCode** | **string** | Required | The code of the Fund referenced by this node. |
| **Role** | **string** | Required | The role of this node within the structure. Must be one of the acceptable values of the structure&#39;s role data type. |
| **AllocationBasis** | [FundStructureAllocationBasis](FundStructureAllocationBasis.md) | Optional | *No description available.* |
| **PnlFlowMode** | **string** | Optional | How profit and loss reaches this member from the members it holds. EquityPickup (the default) revalues the position in each held member; BucketFlowThrough receives one line per economic bucket, tagged with its origin; TransactionFlowThrough receives every line, tagged with its origin and path. Available values: EquityPickup, BucketFlowThrough, TransactionFlowThrough. |
| **AllocationMapId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureNode(
    nodeCode: "...",  // required — A unique identifier for this node within the Fund Structure.
    fundScope: "...",  // required — The scope of the Fund referenced by this node.
    fundCode: "...",  // required — The code of the Fund referenced by this node.
    role: "...",  // required — The role of this node within the structure. Must be one of the acceptable values of the structure&#39;s role data type.
    allocationBasis: new FundStructureAllocationBasis(...),  // optional
    pnlFlowMode: "...",  // optional — How profit and loss reaches this member from the members it holds. EquityPickup (the default) revalues the position in each held member; BucketFlowThrough receives one line per economic bucket, tagged with its origin; TransactionFlowThrough receives every line, tagged with its origin and path. Available values: EquityPickup, BucketFlowThrough, TransactionFlowThrough.
    allocationMapId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureNode>(json);
```

- [FundStructureAllocationBasis](FundStructureAllocationBasis.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

