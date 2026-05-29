# Finbourne.Sdk.Workflow.Model.TriggerChildTasksActionResponse

Defines a read-only Trigger Child Tasks Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Type name for this Action |
| **Trigger** | **string** | Optional | Trigger on child tasks to be invoked |
| **Filter** | **string** | Optional | Optional LUSID filter expression to limit the action to a subset of the child tasks |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerChildTasksActionResponse(
    type: "...",  // optional — Type name for this Action
    trigger: "...",  // optional — Trigger on child tasks to be invoked
    filter: "..."  // optional — Optional LUSID filter expression to limit the action to a subset of the child tasks
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerChildTasksActionResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

