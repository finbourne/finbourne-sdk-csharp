# Finbourne.Sdk.Workflow.Model.ScheduleLauncherDetailsResponse

A Schedule Launcher, which starts a run of its Workflow at the times a recurrence pattern gives
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LauncherType** | **string** | Optional | *No description available.* |
| **Schedule** | [LauncherSchedule](LauncherSchedule.md) | Optional | *No description available.* |
| **CalendarContexts** | [List&lt;CalendarContext&gt;](CalendarContext.md) | Optional | The named time zones and holiday calendars this Launcher works in.              Only a Schedule Launcher works in a calendar context |
| **MapTaskFields** | [Dictionary&lt;string, ScheduleTaskFieldMapping&gt;](ScheduleTaskFieldMapping.md) | Optional | Fields of the root task filled from the instant the schedule fired, keyed by the field name on the root task definition |
| **RunAsUserId** | [LauncherMapping](LauncherMapping.md) | Optional | *No description available.* |
| **SetTaskFields** | **Dictionary&lt;string, Object&gt;** | Optional | Fields of the root task set to a fixed value, keyed by the field name on the root task definition |
| **SetCorrelationIds** | **List&lt;string&gt;** | Optional | Correlation IDs put on the root task as given |
| **InitialTrigger** | **string** | Optional | The trigger given to the root task once it is made and all of its fields are filled, or null when the root task is left in its initial state |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ScheduleLauncherDetailsResponse(
    launcherType: "...",  // optional
    schedule: new LauncherSchedule(...),  // optional
    calendarContexts: new List<CalendarContext>(),  // optional — The named time zones and holiday calendars this Launcher works in.              Only a Schedule Launcher works in a calendar context
    mapTaskFields: new ScheduleTaskFieldMapping(...),  // optional — Fields of the root task filled from the instant the schedule fired, keyed by the field name on the root task definition
    runAsUserId: new LauncherMapping(...),  // optional
    setTaskFields: ,  // optional — Fields of the root task set to a fixed value, keyed by the field name on the root task definition
    setCorrelationIds: ,  // optional — Correlation IDs put on the root task as given
    initialTrigger: "..."  // optional — The trigger given to the root task once it is made and all of its fields are filled, or null when the root task is left in its initial state
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScheduleLauncherDetailsResponse>(json);
```

- [LauncherSchedule](LauncherSchedule.md)
- [CalendarContext](CalendarContext.md) — used in `CalendarContexts`
- [ScheduleTaskFieldMapping](ScheduleTaskFieldMapping.md) — used in `MapTaskFields`
- [LauncherMapping](LauncherMapping.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

