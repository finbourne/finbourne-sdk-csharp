# Finbourne.Sdk.Workflow.Model.WorkflowStructureNodes

The nodes of a Workflow structure graph — the Task Definitions involved
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskDefinitions** | [List&lt;TaskDefinition&gt;](TaskDefinition.md) | Optional | The Task Definitions that make up the nodes of this Workflow |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkflowStructureNodes(
    taskDefinitions: new List<TaskDefinition>()  // optional — The Task Definitions that make up the nodes of this Workflow
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowStructureNodes>(json);
```


## Related Models

- [TaskDefinition](TaskDefinition.md) — used in `TaskDefinitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

