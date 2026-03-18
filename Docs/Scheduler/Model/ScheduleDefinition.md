# Finbourne.Sdk.Scheduler.Model.ScheduleDefinition

Schedule
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ScheduleIdentifier** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **JobId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Name** | **string** | Optional | A display name for this Schedule |
| **Description** | **string** | Optional | A description of the Schedule |
| **Author** | **string** | Optional | Name of the author of this schedule |
| **Owner** | **string** | Optional | Name of owner of this schedule |
| **UseAsAuth** | **string** | Optional | User to runs schedule when automatically run and authenticates  requests in the schedule |
| **Arguments** | **Dictionary&lt;string, string&gt;** | Optional | All arguments specified by this Schedule that will be passed in to the Job |
| **Trigger** | [Trigger](Trigger.md) | Optional | *No description available.* |
| **Notifications** | [List&lt;Notification&gt;](Notification.md) | Optional | Notifications for this Schedule |
| **Enabled** | **bool** | Optional | The status of this schedule |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new ScheduleDefinition(
    scheduleIdentifier: new ResourceId(...),  // required
    jobId: new ResourceId(...),  // optional
    name: "...",  // optional — A display name for this Schedule
    description: "...",  // optional — A description of the Schedule
    author: "...",  // optional — Name of the author of this schedule
    owner: "...",  // optional — Name of owner of this schedule
    useAsAuth: "...",  // optional — User to runs schedule when automatically run and authenticates  requests in the schedule
    arguments: ,  // optional — All arguments specified by this Schedule that will be passed in to the Job
    trigger: new Trigger(...),  // optional
    notifications: new List<Notification>(),  // optional — Notifications for this Schedule
    enabled: true  // optional — The status of this schedule
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScheduleDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Trigger](Trigger.md)
- [Notification](Notification.md) — used in `Notifications`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

