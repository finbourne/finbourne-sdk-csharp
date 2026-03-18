# Finbourne.Sdk.Insights.Model.TraceDiagramNode

Represents a node within a trace diagram.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | Unique identifier of the node. |
| **DisplayName** | **string** | Optional | Display name of the node. |
| **Level** | **int** | Optional | Depth level of the node within the diagram. |
| **Parent** | **string** | Optional | Identifier of the node&#39;s parent. This is null for the root node. |
| **Type** | **string** | Optional | Type classification of the node. |
| **AgentScope** | **string** | Optional | The scope of the agent. |
| **AgentVersion** | **int** | Optional | The version of the agent. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new TraceDiagramNode(
    id: "...",  // optional — Unique identifier of the node.
    displayName: "...",  // optional — Display name of the node.
    level: 0,  // optional — Depth level of the node within the diagram.
    parent: "...",  // optional — Identifier of the node&#39;s parent. This is null for the root node.
    type: "...",  // optional — Type classification of the node.
    agentScope: "...",  // optional — The scope of the agent.
    agentVersion: 0  // optional — The version of the agent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TraceDiagramNode>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

