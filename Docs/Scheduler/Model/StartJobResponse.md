# Finbourne.Sdk.Scheduler.Model.StartJobResponse

Response from starting a job
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **JobId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **RunId** | **string** | Optional | Unique RunId of the started job run |
| **Status** | **string** | Optional | Link to the status of the started job |
| **Result** | **string** | Optional | Link to the result of the job run when completed |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new StartJobResponse(
    jobId: new ResourceId(...),  // optional
    runId: "...",  // optional — Unique RunId of the started job run
    status: "...",  // optional — Link to the status of the started job
    result: "..."  // optional — Link to the result of the job run when completed
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StartJobResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

