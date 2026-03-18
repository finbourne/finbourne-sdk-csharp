# Finbourne.Sdk.Workflow.Model.TriggerParentTaskAction

Defines a Trigger Parent Task Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | Type name for this Action |
| **Trigger** | **string** | Required | Trigger on parent task to be invoked |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerParentTaskAction(
    type: "...",  // required — Type name for this Action
    trigger: "..."  // required — Trigger on parent task to be invoked
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerParentTaskAction>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

