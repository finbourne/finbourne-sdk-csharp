# Finbourne.Sdk.Lusid.Model.FundStructure

Definition of the structure of a fund
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Required | The display name of the Fund Structure. |
| **Description** | **string** | Optional | An optional description for the Fund Structure. |
| **Funds** | [List&lt;Fund&gt;](Fund.md) | Optional | An optional list of existing funds to be incorporated as part of the structure. |
| **AllocationGroups** | [List&lt;AllocationGroup&gt;](AllocationGroup.md) | Optional | An optional list of Allocation Groups that can apply across a Fund Structure. Only classes and feeder funds linked to the master fund specified are allowed. |
| **Nodes** | [List&lt;FundStructureNode&gt;](FundStructureNode.md) | Required | The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role. |
| **Edges** | [List&lt;FundStructureEdge&gt;](FundStructureEdge.md) | Required | The list of edges that define the relationships between feeder and master nodes in the structure. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Fund Structure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructure(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    name: "...",  // required — The display name of the Fund Structure.
    description: "...",  // optional — An optional description for the Fund Structure.
    funds: new List<Fund>(),  // optional — An optional list of existing funds to be incorporated as part of the structure.
    allocationGroups: new List<AllocationGroup>(),  // optional — An optional list of Allocation Groups that can apply across a Fund Structure. Only classes and feeder funds linked to the master fund specified are allowed.
    nodes: new List<FundStructureNode>(),  // required — The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role.
    edges: new List<FundStructureEdge>(),  // required — The list of edges that define the relationships between feeder and master nodes in the structure.
    varVersion: new ModelVersion(...),  // optional
    properties: new Property(...),  // optional — A set of properties to decorate onto the Fund Structure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructure>(json);
```

- [ResourceId](ResourceId.md)
- [Fund](Fund.md) — used in `Funds`
- [AllocationGroup](AllocationGroup.md) — used in `AllocationGroups`
- [FundStructureNode](FundStructureNode.md) — used in `Nodes`
- [FundStructureEdge](FundStructureEdge.md) — used in `Edges`
- [ModelVersion](ModelVersion.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

