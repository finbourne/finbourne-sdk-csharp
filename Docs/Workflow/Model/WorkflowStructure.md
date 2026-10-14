# Finbourne.Sdk.Workflow.Model.WorkflowStructure

Describes the structure of a Workflow as a graph of its Task Definitions and its Launchers
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Nodes** | [WorkflowStructureNodes](WorkflowStructureNodes.md) | Optional | *No description available.* |
| **Edges** | [WorkflowStructureEdges](WorkflowStructureEdges.md) | Optional | *No description available.* |
| **LaunchersTruncated** | **bool** | Optional | True when the Workflow has more Launchers than were returned inline in nodes.launchers. Call ListLaunchers for the full set |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkflowStructure(
    nodes: new WorkflowStructureNodes(...),  // optional
    edges: new WorkflowStructureEdges(...),  // optional
    launchersTruncated: true  // optional — True when the Workflow has more Launchers than were returned inline in nodes.launchers. Call ListLaunchers for the full set
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowStructure>(json);
```


## Related Models

- [WorkflowStructureNodes](WorkflowStructureNodes.md)
- [WorkflowStructureEdges](WorkflowStructureEdges.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

