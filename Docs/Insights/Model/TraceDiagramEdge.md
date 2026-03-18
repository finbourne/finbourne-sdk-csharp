# Finbourne.Sdk.Insights.Model.TraceDiagramEdge

Represents an edge connecting two nodes within a trace diagram.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **int** | Optional | Sequential identifier of the edge. |
| **NodeId** | **string** | Optional | Identifier of the parent node. |
| **ChildNodeId** | **string** | Optional | Identifier of the child node. |
| **Label** | **string** | Optional | Label displayed for the edge. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TraceDiagramEdge(
    id: 0,  // optional — Sequential identifier of the edge.
    nodeId: "...",  // optional — Identifier of the parent node.
    childNodeId: "...",  // optional — Identifier of the child node.
    label: "..."  // optional — Label displayed for the edge.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TraceDiagramEdge>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

