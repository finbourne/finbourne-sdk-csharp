# Finbourne.Sdk.Horizon.Model.InstanceRunResponse

Response containing details of a single run for an instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **Guid** | Required | *No description available.* |
| **BatchReferenceId** | **Guid** | Required | *No description available.* |
| **Attempt** | **int?** | Optional | *No description available.* |
| **StartTime** | **DateTimeOffset** | Required | *No description available.* |
| **EndTime** | **DateTimeOffset?** | Optional | *No description available.* |
| **Duration** | **string** | Optional | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **TriggeredBy** | **string** | Optional | *No description available.* |
| **Total** | **int** | Required | *No description available.* |
| **SentCount** | **long** | Required | *No description available.* |
| **SkippedCount** | **long** | Required | *No description available.* |
| **FailedCount** | **long** | Required | *No description available.* |
| **FailedFiles** | **int** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceRunResponse(
    runId: "...",  // required
    batchReferenceId: "...",  // required
    attempt: 0,  // optional
    startTime: DateTimeOffset.Now,  // required
    endTime: DateTimeOffset.Now,  // optional
    duration: "...",  // optional
    status: "...",  // required
    triggeredBy: "...",  // optional
    total: 0,  // required
    sentCount: 0L,  // required
    skippedCount: 0L,  // required
    failedCount: 0L,  // required
    failedFiles: 0  // required
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

