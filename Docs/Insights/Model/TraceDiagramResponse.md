# Finbourne.Sdk.Insights.Model.TraceDiagramResponse

Represents a trace diagram composed of nodes and edges.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Nodes** | [List&lt;TraceDiagramNode&gt;](TraceDiagramNode.md) | Optional | The nodes that make up the diagram. |
| **Edges** | [List&lt;TraceDiagramEdge&gt;](TraceDiagramEdge.md) | Optional | The edges that connect the nodes in the diagram. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TraceDiagramResponse(
    nodes: new List<TraceDiagramNode>(),  // optional — The nodes that make up the diagram.
    edges: new List<TraceDiagramEdge>()  // optional — The edges that connect the nodes in the diagram.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TraceDiagramResponse>(json);
```


## Related Models

- [TraceDiagramNode](TraceDiagramNode.md) — used in `Nodes`
- [TraceDiagramEdge](TraceDiagramEdge.md) — used in `Edges`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

