# Finbourne.Sdk.Workflow.Model.TriggerNextTaskFallbackActions

Actions on the same task definition that a Trigger Next Task action runs instead of triggering the next task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EndOfSequence** | **string** | Optional | Run when this task has no next task to trigger |
| **NextTaskError** | **string** | Optional | Run when the next task cannot be triggered, e.g. it was deleted or is not in its initial state |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerNextTaskFallbackActions(
    endOfSequence: "...",  // optional — Run when this task has no next task to trigger
    nextTaskError: "..."  // optional — Run when the next task cannot be triggered, e.g. it was deleted or is not in its initial state
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerNextTaskFallbackActions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

