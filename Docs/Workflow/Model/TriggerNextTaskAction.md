# Finbourne.Sdk.Workflow.Model.TriggerNextTaskAction

Defines a Trigger Next Task Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | Type name for this Action |
| **DefaultTrigger** | **string** | Optional | Trigger sent to the next task when this task has no nextTaskInitialTrigger of its own |
| **FallbackActions** | [TriggerNextTaskFallbackActions](TriggerNextTaskFallbackActions.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerNextTaskAction(
    type: "...",  // required — Type name for this Action
    defaultTrigger: "...",  // optional — Trigger sent to the next task when this task has no nextTaskInitialTrigger of its own
    fallbackActions: new TriggerNextTaskFallbackActions(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerNextTaskAction>(json);
```

- [TriggerNextTaskFallbackActions](TriggerNextTaskFallbackActions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

