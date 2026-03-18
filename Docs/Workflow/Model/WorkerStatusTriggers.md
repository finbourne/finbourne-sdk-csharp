# Finbourne.Sdk.Workflow.Model.WorkerStatusTriggers

Defines triggers that will be invoked per Worker outcome
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Started** | **string** | Optional | Trigger to invoke when the Worker has Started |
| **CompletedWithResults** | **string** | Optional | Trigger to invoke when the Worker has Completed (with results) |
| **CompletedNoResults** | **string** | Optional | Trigger to invoke when the Worker has Completed (no results) |
| **FailedToStart** | **string** | Optional | Trigger to invoke when the Worker has Failed to Start |
| **FailedToComplete** | **string** | Optional | Trigger to invoke when the Worker has Failed to Complete |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkerStatusTriggers(
    started: "...",  // optional — Trigger to invoke when the Worker has Started
    completedWithResults: "...",  // optional — Trigger to invoke when the Worker has Completed (with results)
    completedNoResults: "...",  // optional — Trigger to invoke when the Worker has Completed (no results)
    failedToStart: "...",  // optional — Trigger to invoke when the Worker has Failed to Start
    failedToComplete: "..."  // optional — Trigger to invoke when the Worker has Failed to Complete
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkerStatusTriggers>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

