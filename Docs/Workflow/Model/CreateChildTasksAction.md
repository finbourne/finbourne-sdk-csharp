# Finbourne.Sdk.Workflow.Model.CreateChildTasksAction

Defines a Create Child Tasks Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | Type name for this Action |
| **ChildTaskConfigurations** | [List&lt;CreateChildTaskConfiguration&gt;](CreateChildTaskConfiguration.md) | Required | The Child Task Configurations |
| **Ordering** | **string** | Optional | How the created child tasks are ordered for execution: Parallel (default) or Series. In Series the child tasks form a chain and only the first is started; each later one is started by its predecessor&#39;s TriggerNextTask action, or by another trigger such as a TriggerChildTasks filter on previousTask. Without one, the chain stops after the first child. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateChildTasksAction(
    type: "...",  // required — Type name for this Action
    childTaskConfigurations: new List<CreateChildTaskConfiguration>(),  // required — The Child Task Configurations
    ordering: "..."  // optional — How the created child tasks are ordered for execution: Parallel (default) or Series. In Series the child tasks form a chain and only the first is started; each later one is started by its predecessor&#39;s TriggerNextTask action, or by another trigger such as a TriggerChildTasks filter on previousTask. Without one, the chain stops after the first child.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateChildTasksAction>(json);
```

- [CreateChildTaskConfiguration](CreateChildTaskConfiguration.md) — used in `ChildTaskConfigurations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

