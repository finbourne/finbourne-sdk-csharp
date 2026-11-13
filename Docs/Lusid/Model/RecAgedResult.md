# Finbourne.Sdk.Lusid.Model.RecAgedResult

A summary of a rec result in another instance, as at the stamp that first recorded it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The id of the result within its instance, e.g. &#39;Holding-break-1&#39;. With instanceId, it fully qualifies the result. |
| **InstanceId** | [RecInstanceId](RecInstanceId.md) | Required | *No description available.* |
| **RunNumber** | **int** | Required | The result&#39;s latest run as at the stamp that first recorded it. |
| **RunAsAt** | **DateTimeOffset** | Required | The asAt datetime of the result&#39;s latest run as at the stamp that first recorded it. |
| **FirstRunSeen** | **int** | Required | The run in which the result was first assigned its id. |
| **AsAtFirstSeen** | **DateTimeOffset** | Required | The runAsAt of the run in which the result first appeared in its instance, the run numbered firstRunSeen. Written once: re-runs leave it unchanged. |
| **DatesReconciled** | [RecDatesReconciled](RecDatesReconciled.md) | Required | *No description available.* |
| **ExceptionStatus** | **string** | Required | The result&#39;s exception status as at the stamp that first recorded it: Open or Closed. Available values: Open, Closed. |
| **ClosureType** | **string** | Optional | The result&#39;s exception closure type as at the stamp that first recorded it. Null while the exception is open. Available values: Cleared, Accepted, ForceMatched. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecAgedResult(
    id: "...",  // required — The id of the result within its instance, e.g. &#39;Holding-break-1&#39;. With instanceId, it fully qualifies the result.
    instanceId: new RecInstanceId(...),  // required
    runNumber: 0,  // required — The result&#39;s latest run as at the stamp that first recorded it.
    runAsAt: DateTimeOffset.Now,  // required — The asAt datetime of the result&#39;s latest run as at the stamp that first recorded it.
    firstRunSeen: 0,  // required — The run in which the result was first assigned its id.
    asAtFirstSeen: DateTimeOffset.Now,  // required — The runAsAt of the run in which the result first appeared in its instance, the run numbered firstRunSeen. Written once: re-runs leave it unchanged.
    datesReconciled: new RecDatesReconciled(...),  // required
    exceptionStatus: "...",  // required — The result&#39;s exception status as at the stamp that first recorded it: Open or Closed. Available values: Open, Closed.
    closureType: "..."  // optional — The result&#39;s exception closure type as at the stamp that first recorded it. Null while the exception is open. Available values: Cleared, Accepted, ForceMatched.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecAgedResult>(json);
```

- [RecInstanceId](RecInstanceId.md)
- [RecDatesReconciled](RecDatesReconciled.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

