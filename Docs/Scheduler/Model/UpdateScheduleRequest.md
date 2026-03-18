# Finbourne.Sdk.Scheduler.Model.UpdateScheduleRequest

Create a schedule definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **JobId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Required | The updated name of the schedule |
| **Description** | **string** | Required | The updated description of the schedule |
| **Author** | **string** | Optional | The updated author of the schedule |
| **Owner** | **string** | Optional | The update owner of the schedule |
| **Arguments** | **Dictionary&lt;string, string&gt;** | Optional | Updated arguments to be passed to the job Note: The new arguments will completely replace old arguments |
| **Trigger** | [Trigger](Trigger.md) | Optional | *No description available.* |
| **Notifications** | [List&lt;Notification&gt;](Notification.md) | Optional | Updated notifications for this schedule |
| **Enabled** | **bool** | Optional | Specify whether schedule is enabled or not Defaults to true |
| **UseAsAuth** | **string** | Optional | Id of user associated with schedule. All calls to FINBOURNE services as part of execution of this schedule will be authenticated as this  user. Can be null, in which case we&#39;ll default to that of the user  making this request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Scheduler.Model;

var instance = new UpdateScheduleRequest(
    jobId: new ResourceId(...),  // required
    name: "...",  // required — The updated name of the schedule
    description: "...",  // required — The updated description of the schedule
    author: "...",  // optional — The updated author of the schedule
    owner: "...",  // optional — The update owner of the schedule
    arguments: ,  // optional — Updated arguments to be passed to the job Note: The new arguments will completely replace old arguments
    trigger: new Trigger(...),  // optional
    notifications: new List<Notification>(),  // optional — Updated notifications for this schedule
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
var instance = JsonConvert.DeserializeObject<UpdateScheduleRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [Trigger](Trigger.md)
- [Notification](Notification.md) — used in `Notifications`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

