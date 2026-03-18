# Finbourne.Sdk.Workflow.Model.TriggerParentTaskActionResponse

Defines a read-only Trigger Parent Task Action
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Type name for this Action |
| **Trigger** | **string** | Optional | Trigger on parent task to be invoked |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TriggerParentTaskActionResponse(
    type: "...",  // optional — Type name for this Action
    trigger: "..."  // optional — Trigger on parent task to be invoked
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TriggerParentTaskActionResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

