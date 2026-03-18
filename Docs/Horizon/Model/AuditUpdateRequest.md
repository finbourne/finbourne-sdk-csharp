# Finbourne.Sdk.Horizon.Model.AuditUpdateRequest

An incoming request for a Horizon Update Event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | A unique ID identifiying the source of the event |
| **UserId** | **string** | Required | A unique ID identifiying who owns the schedule |
| **SchedulerRunId** | **string** | Required | The GUID of the schedule run |
| **StartTime** | **DateTimeOffset** | Required | When the run was started in UTC |
| **Message** | **string** | Required | A descriptive message to accompany the status |
| **ProcessNameOverride** | **string** | Optional | Optional Name for how the process appears in Data Feed Monitoring |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new AuditUpdateRequest(
    id: "...",  // required — A unique ID identifiying the source of the event
    userId: "...",  // required — A unique ID identifiying who owns the schedule
    schedulerRunId: "...",  // required — The GUID of the schedule run
    startTime: DateTimeOffset.Now,  // required — When the run was started in UTC
    message: "...",  // required — A descriptive message to accompany the status
    processNameOverride: "..."  // optional — Optional Name for how the process appears in Data Feed Monitoring
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditUpdateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

