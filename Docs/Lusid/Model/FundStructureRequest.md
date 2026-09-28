# Finbourne.Sdk.Lusid.Model.FundStructureRequest

The request used to create a Fund Structure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Fund Structure. |
| **Name** | **string** | Required | The display name of the Fund Structure. |
| **Description** | **string** | Optional | An optional description for the Fund Structure. |
| **ExistingFunds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | An optional list of existing funds to be incorporated as part of the structure. |
| **AllocationGroups** | [List&lt;AllocationGroup&gt;](AllocationGroup.md) | Optional | An optional list of Allocation Groups that can apply across a Fund Structure. A group may span the share classes of a member and the members that invest into it through dedicated share class links. |
| **Nodes** | [List&lt;FundStructureNode&gt;](FundStructureNode.md) | Optional | The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role. May be empty on create, with members added later through the members endpoint. |
| **Edges** | [List&lt;FundStructureEdge&gt;](FundStructureEdge.md) | Optional | The list of edges that define how the members of the structure are linked: a member investing into a dedicated share class of another, or holding an equity, GP, LP or carry interest in another through an instrument. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime from which the Fund Structure applies. Defaults to the beginning of time if not specified, so that the structure is visible at every effective datetime. |
| **RoleDataTypeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **NavTypeCodes** | **List&lt;string&gt;** | Required | The NAV types every member of the structure produces, by code. Declaring them once here gives the structure a shared Timeline. At least one is required, and every member fund must define a NAV type with each of these codes. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties to decorate onto the Fund Structure. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureRequest(
    code: "...",  // required — The code of the Fund Structure.
    name: "...",  // required — The display name of the Fund Structure.
    description: "...",  // optional — An optional description for the Fund Structure.
    existingFunds: new List<ResourceId>(),  // optional — An optional list of existing funds to be incorporated as part of the structure.
    allocationGroups: new List<AllocationGroup>(),  // optional — An optional list of Allocation Groups that can apply across a Fund Structure. A group may span the share classes of a member and the members that invest into it through dedicated share class links.
    nodes: new List<FundStructureNode>(),  // optional — The list of nodes that make up the Fund Structure, each referencing a Fund and defining its role. May be empty on create, with members added later through the members endpoint.
    edges: new List<FundStructureEdge>(),  // optional — The list of edges that define how the members of the structure are linked: a member investing into a dedicated share class of another, or holding an equity, GP, LP or carry interest in another through an instrument.
    effectiveAt: DateTimeOffset.Now,  // optional — The effective datetime from which the Fund Structure applies. Defaults to the beginning of time if not specified, so that the structure is visible at every effective datetime.
    roleDataTypeId: new ResourceId(...),  // optional
    navTypeCodes: ,  // required — The NAV types every member of the structure produces, by code. Declaring them once here gives the structure a shared Timeline. At least one is required, and every member fund must define a NAV type with each of these codes.
    properties: new Property(...)  // optional — A set of properties to decorate onto the Fund Structure.
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
- [AllocationGroup](AllocationGroup.md) — used in `AllocationGroups`
- [FundStructureNode](FundStructureNode.md) — used in `Nodes`
- [FundStructureEdge](FundStructureEdge.md) — used in `Edges`
- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

