# Finbourne.Sdk.Lusid.Model.RecWorkflowTask

The workflow service task that instantiated a rec instance.  Minimal placeholder until the full workflow service task DTO is available.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The identifier of the workflow service task. |
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **State** | **string** | Optional | The current state of the workflow service task. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecWorkflowTask(
    id: "...",  // optional — The identifier of the workflow service task.
    taskDefinitionId: new ResourceId(...),  // optional
    state: "..."  // optional — The current state of the workflow service task.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecWorkflowTask>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

