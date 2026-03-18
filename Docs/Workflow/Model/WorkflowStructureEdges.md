# Finbourne.Sdk.Workflow.Model.WorkflowStructureEdges

The edges of a Workflow structure graph — the parent-child relationships between Task Definitions
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ChildTaskDefinitions** | [List&lt;ChildTaskDefinitionEdge&gt;](ChildTaskDefinitionEdge.md) | Optional | The child Task Definition relationships |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkflowStructureEdges(
    childTaskDefinitions: new List<ChildTaskDefinitionEdge>()  // optional — The child Task Definition relationships
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowStructureEdges>(json);
```


## Related Models

- [ChildTaskDefinitionEdge](ChildTaskDefinitionEdge.md) — used in `ChildTaskDefinitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

