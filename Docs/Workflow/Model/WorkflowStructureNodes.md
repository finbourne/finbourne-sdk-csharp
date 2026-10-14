# Finbourne.Sdk.Workflow.Model.WorkflowStructureNodes

The nodes of a Workflow structure graph — the Task Definitions and the Launchers involved
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskDefinitions** | [List&lt;TaskDefinition&gt;](TaskDefinition.md) | Optional | The Task Definitions that make up the nodes of this Workflow |
| **Launchers** | [List&lt;LauncherResponse&gt;](LauncherResponse.md) | Optional | The Launchers of this Workflow, as full Launcher objects. At most the first 10 by launcher id are returned, in the same order as ListLaunchers gives by default. Inactive Launchers are included. When the Workflow has more, launchersTruncated is true and ListLaunchers returns the full set |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkflowStructureNodes(
    taskDefinitions: new List<TaskDefinition>(),  // optional — The Task Definitions that make up the nodes of this Workflow
    launchers: new List<LauncherResponse>()  // optional — The Launchers of this Workflow, as full Launcher objects. At most the first 10 by launcher id are returned, in the same order as ListLaunchers gives by default. Inactive Launchers are included. When the Workflow has more, launchersTruncated is true and ListLaunchers returns the full set
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
- [LauncherResponse](LauncherResponse.md) — used in `Launchers`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

