# Finbourne.Sdk.Workflow.Model.TriggerNextTaskActionResponse

Trigger Next Task Action Response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Type name for this Action |
| **DefaultTrigger** | **string** | Optional | Trigger sent to the next task when this task has no nextTaskInitialTrigger of its own |
| **FallbackActions** | [TriggerNextTaskFallbackActionsResponse](TriggerNextTaskFallbackActionsResponse.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerNextTaskActionResponse(
    type: "...",  // optional — Type name for this Action
    defaultTrigger: "...",  // optional — Trigger sent to the next task when this task has no nextTaskInitialTrigger of its own
    fallbackActions: new TriggerNextTaskFallbackActionsResponse(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerNextTaskActionResponse>(json);
```

- [TriggerNextTaskFallbackActionsResponse](TriggerNextTaskFallbackActionsResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

