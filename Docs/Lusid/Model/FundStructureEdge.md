# Finbourne.Sdk.Lusid.Model.FundStructureEdge

A directed edge in a Fund Structure, defining a relationship from a feeder node to a master node share class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **From** | **string** | Required | The node code of the feeder node that is the source of this relationship. |
| **To** | [FundStructureEdgeTarget](FundStructureEdgeTarget.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureEdge(
    from: "...",  // required — The node code of the feeder node that is the source of this relationship.
    to: new FundStructureEdgeTarget(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureEdge>(json);
```

- [FundStructureEdgeTarget](FundStructureEdgeTarget.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

