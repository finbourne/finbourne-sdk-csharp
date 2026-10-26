# Finbourne.Sdk.Horizon.Model.InstanceRunResponse

Response containing details of a single run for an instance. The transaction and file figures describe the batch as it stands now, so they are reported on the latest attempt only and are null on earlier attempts of a retried run. Message explains a failed attempt and what will happen or must be done next; it is null for completed, running and queued attempts.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **Guid** | Required | *No description available.* |
| **ReferenceId** | **Guid** | Required | *No description available.* |
| **Attempt** | **int?** | Optional | *No description available.* |
| **StartTime** | **DateTimeOffset** | Required | *No description available.* |
| **EndTime** | **DateTimeOffset?** | Optional | *No description available.* |
| **Duration** | **string** | Optional | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **TriggeredBy** | **string** | Optional | *No description available.* |
| **Total** | **int?** | Optional | *No description available.* |
| **SentCount** | **long?** | Optional | *No description available.* |
| **SkippedCount** | **long?** | Optional | *No description available.* |
| **FailedCount** | **long?** | Optional | *No description available.* |
| **FailedFiles** | **int?** | Optional | *No description available.* |
| **Message** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceRunResponse(
    runId: "...",  // required
    referenceId: "...",  // required
    attempt: 0,  // optional
    startTime: DateTimeOffset.Now,  // required
    endTime: DateTimeOffset.Now,  // optional
    duration: "...",  // optional
    status: "...",  // required
    triggeredBy: "...",  // optional
    total: 0,  // optional
    sentCount: 0L,  // optional
    skippedCount: 0L,  // optional
    failedCount: 0L,  // optional
    failedFiles: 0,  // optional
    message: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstanceRunResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

