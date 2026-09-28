# Finbourne.Sdk.Lusid.Model.FundStructureMemberRequest

A member to add to a Fund Structure: the node, and the links that join it to members already in the structure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Node** | [FundStructureNode](FundStructureNode.md) | Required | *No description available.* |
| **Edges** | [List&lt;FundStructureEdge&gt;](FundStructureEdge.md) | Optional | The links joining the new node to members already in the structure. May be empty for a member that is linked later. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureMemberRequest(
    node: new FundStructureNode(...),  // required
    edges: new List<FundStructureEdge>()  // optional — The links joining the new node to members already in the structure. May be empty for a member that is linked later.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureMemberRequest>(json);
```


## Related Models

- [FundStructureNode](FundStructureNode.md)
- [FundStructureEdge](FundStructureEdge.md) — used in `Edges`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

