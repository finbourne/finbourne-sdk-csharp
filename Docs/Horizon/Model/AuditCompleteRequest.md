# Finbourne.Sdk.Horizon.Model.AuditCompleteRequest

An incoming request for a Horizon Complete Event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | A unique ID identifiying the source of the event |
| **UserId** | **string** | Required | A unique ID identifiying who owns the schedule |
| **SchedulerRunId** | **string** | Required | The GUID of the schedule run |
| **StartTime** | **DateTimeOffset** | Required | When the run was started in UTC |
| **EndTime** | **DateTimeOffset** | Required | When the run finished in UTC |
| **Message** | **string** | Required | A descriptive message to accompany the status |
| **Status** | **string** | Required | The final status of the run |
| **RowsTotal** | **int** | Required | The number of data rows operated on |
| **RowsSucceeded** | **int** | Required | The number of data rows successfully operated on |
| **RowsFailed** | **int** | Required | The number of data rows that failed to be operated on |
| **RowsIgnored** | **int** | Required | The number of data rows that had no actions taken |
| **AuditFiles** | [List&lt;AuditFileDetails&gt;](AuditFileDetails.md) | Required | A list of file details for attaching to the event |
| **ProcessNameOverride** | **string** | Optional | Optional Name for how the process appears in Data Feed Monitoring |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new AuditCompleteRequest(
    id: "...",  // required — A unique ID identifiying the source of the event
    userId: "...",  // required — A unique ID identifiying who owns the schedule
    schedulerRunId: "...",  // required — The GUID of the schedule run
    startTime: DateTimeOffset.Now,  // required — When the run was started in UTC
    endTime: DateTimeOffset.Now,  // required — When the run finished in UTC
    message: "...",  // required — A descriptive message to accompany the status
    status: "...",  // required — The final status of the run
    rowsTotal: 0,  // required — The number of data rows operated on
    rowsSucceeded: 0,  // required — The number of data rows successfully operated on
    rowsFailed: 0,  // required — The number of data rows that failed to be operated on
    rowsIgnored: 0,  // required — The number of data rows that had no actions taken
    auditFiles: new List<AuditFileDetails>(),  // required — A list of file details for attaching to the event
    processNameOverride: "..."  // optional — Optional Name for how the process appears in Data Feed Monitoring
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditCompleteRequest>(json);
```

- [AuditFileDetails](AuditFileDetails.md) — used in `AuditFiles`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

