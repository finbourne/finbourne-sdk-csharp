# Finbourne.Sdk.Workflow.Model.TriggerChildTasksAction

Defines a Trigger Child Tasks Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | Type name for this Action |
| **Trigger** | **string** | Required | Trigger on child tasks to be invoked |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerChildTasksAction(
    type: "...",  // required — Type name for this Action
    trigger: "..."  // required — Trigger on child tasks to be invoked
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerChildTasksAction>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

