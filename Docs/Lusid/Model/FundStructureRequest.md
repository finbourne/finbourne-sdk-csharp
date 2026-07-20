# Finbourne.Sdk.Lusid.Model.FundStructureRequest

The request used to create a Fund Structure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Fund Structure. |
| **Name** | **string** | Required | The display name of the Fund Structure. |
| **Description** | **string** | Optional | An optional description for the Fund Structure. |
| **ExistingFunds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | An optional list of existing funds to be incorporated as part of the structure. |
| **NewFunds** | [List&lt;FundDefinitionRequest&gt;](FundDefinitionRequest.md) | Optional | An optional list of Fund definitions to be created inline as part of the structure. |
| **AllocationGroups** | [List&lt;AllocationGroup&gt;](AllocationGroup.md) | Optional | An optional list of Allocation Groups that can apply across a Fund Structure. Only classes and feeder funds linked to the master fund specified are allowed. |
| **Nodes** | [List&lt;FundStructureNode&gt;](FundStructureNode.md) | Required | The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role. |
| **Edges** | [List&lt;FundStructureEdge&gt;](FundStructureEdge.md) | Required | The list of edges that define the relationships between feeder and master nodes in the structure. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureRequest(
    code: "...",  // required — The code of the Fund Structure.
    name: "...",  // required — The display name of the Fund Structure.
    description: "...",  // optional — An optional description for the Fund Structure.
    existingFunds: new List<ResourceId>(),  // optional — An optional list of existing funds to be incorporated as part of the structure.
    newFunds: new List<FundDefinitionRequest>(),  // optional — An optional list of Fund definitions to be created inline as part of the structure.
    allocationGroups: new List<AllocationGroup>(),  // optional — An optional list of Allocation Groups that can apply across a Fund Structure. Only classes and feeder funds linked to the master fund specified are allowed.
    nodes: new List<FundStructureNode>(),  // required — The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role.
    edges: new List<FundStructureEdge>()  // required — The list of edges that define the relationships between feeder and master nodes in the structure.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureRequest>(json);
```

- [ResourceId](ResourceId.md) — used in `ExistingFunds`
- [FundDefinitionRequest](FundDefinitionRequest.md) — used in `NewFunds`
- [AllocationGroup](AllocationGroup.md) — used in `AllocationGroups`
- [FundStructureNode](FundStructureNode.md) — used in `Nodes`
- [FundStructureEdge](FundStructureEdge.md) — used in `Edges`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

