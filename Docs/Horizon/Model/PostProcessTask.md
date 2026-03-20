# Finbourne.Sdk.Horizon.Model.PostProcessTask

Request defining a post-processing task for an instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Action** | **string** | Required | The type of action to perform (Allowed: RunIntegration, RunWorkflow, TriggerEmail) |
| **TargetInstance** | **string** | Optional | The instance identifier to trigger (for TriggerIntegration action). |
| **TriggerOn** | **string** | Required | When the task should be triggered (Allowed: OnSuccess, OnFailure, Always) |
| **Parameters** | **Object** | Optional | JSON parameters specific to the action type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new PostProcessTask(
    action: "...",  // required — The type of action to perform (Allowed: RunIntegration, RunWorkflow, TriggerEmail)
    targetInstance: "...",  // optional — The instance identifier to trigger (for TriggerIntegration action).
    triggerOn: "...",  // required — When the task should be triggered (Allowed: OnSuccess, OnFailure, Always)
    parameters:   // optional — JSON parameters specific to the action type.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostProcessTask>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

