# Finbourne.Sdk.Scheduler.Model.StartScheduleResponse

Response from a manual run of a schedule
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ScheduleId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **JobId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **RunId** | **string** | Optional | Unique RunId of the started schedule |
| **Status** | **string** | Optional | Status of the started schedule |
| **Result** | **string** | Optional | Link to the result of the job run when completed |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new StartScheduleResponse(
    scheduleId: new ResourceId(...),  // optional
    jobId: new ResourceId(...),  // optional
    runId: "...",  // optional — Unique RunId of the started schedule
    status: "...",  // optional — Status of the started schedule
    result: "..."  // optional — Link to the result of the job run when completed
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StartScheduleResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

