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
| **AllocationGroups** | [List&lt;AllocationGroup&gt;](AllocationGroup.md) | Optional | An optional list of Allocation Groups that can apply across a Fund Structure. A group may span the share classes of a member and the members that invest into it through dedicated share class links. |
| **Nodes** | [List&lt;FundStructureNode&gt;](FundStructureNode.md) | Required | The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role. May be empty on create, with members added later through the members endpoint. |
| **Edges** | [List&lt;FundStructureEdge&gt;](FundStructureEdge.md) | Required | The list of edges that define how the members of the structure are linked: a member investing into a dedicated share class of another, or holding an equity, GP, LP or carry interest in another through an instrument. |
| **RoleDataTypeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **NavTypeCodes** | **List&lt;string&gt;** | Optional | The NAV types every member of the structure produces, by code. Declaring them once here gives the structure a shared Timeline. At least one is required, and every member fund must define a NAV type with each of these codes. |
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
    allocationGroups: new List<AllocationGroup>(),  // optional — An optional list of Allocation Groups that can apply across a Fund Structure. A group may span the share classes of a member and the members that invest into it through dedicated share class links.
    nodes: new List<FundStructureNode>(),  // required — The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role. May be empty on create, with members added later through the members endpoint.
    edges: new List<FundStructureEdge>(),  // required — The list of edges that define how the members of the structure are linked: a member investing into a dedicated share class of another, or holding an equity, GP, LP or carry interest in another through an instrument.
    roleDataTypeId: new ResourceId(...),  // optional
    navTypeCodes: ,  // optional — The NAV types every member of the structure produces, by code. Declaring them once here gives the structure a shared Timeline. At least one is required, and every member fund must define a NAV type with each of these codes.
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
- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

