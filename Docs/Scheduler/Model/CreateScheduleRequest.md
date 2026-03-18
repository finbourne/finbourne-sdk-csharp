# Finbourne.Sdk.Scheduler.Model.CreateScheduleRequest

Create a schedule definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ScheduleId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **JobId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Required | A display name for this Schedule |
| **Description** | **string** | Required | A description of the Schedule |
| **Author** | **string** | Optional | Name of the author of this schedule |
| **Owner** | **string** | Optional | Name of owner of this schedule |
| **Arguments** | **Dictionary&lt;string, string&gt;** | Optional | All arguments specified by this Schedule that will be passed in to the Job |
| **Trigger** | [Trigger](Trigger.md) | Optional | *No description available.* |
| **Notifications** | [List&lt;Notification&gt;](Notification.md) | Optional | Notifications for this Schedule |
| **Enabled** | **bool** | Optional | Specify whether schedule is enabled or not Defaults to true |
| **UseAsAuth** | **string** | Optional | Id of user associated with schedule. All calls to FINBOURNE services as part of execution of this schedule will be authenticated as this  user. Can be null, in which case we&#39;ll default to that of the user  making this request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new CreateScheduleRequest(
    scheduleId: new ResourceId(...),  // required
    jobId: new ResourceId(...),  // required
    name: "...",  // required — A display name for this Schedule
    description: "...",  // required — A description of the Schedule
    author: "...",  // optional — Name of the author of this schedule
    owner: "...",  // optional — Name of owner of this schedule
    arguments: ,  // optional — All arguments specified by this Schedule that will be passed in to the Job
    trigger: new Trigger(...),  // optional
    notifications: new List<Notification>(),  // optional — Notifications for this Schedule
    enabled: true,  // optional — Specify whether schedule is enabled or not Defaults to true
    useAsAuth: "..."  // optional — Id of user associated with schedule. All calls to FINBOURNE services as part of execution of this schedule will be authenticated as this  user. Can be null, in which case we&#39;ll default to that of the user  making this request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateScheduleRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Trigger](Trigger.md)
- [Notification](Notification.md) — used in `Notifications`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

