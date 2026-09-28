# Finbourne.Sdk.Workflow.Model.LauncherSchedule

When a Schedule Launcher starts a run of its Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalendarContext** | **string** | Required | The name of the calendar context the schedule is read in, which must be one the Launcher declares |
| **RecurrencePattern** | [RecurrencePattern](RecurrencePattern.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LauncherSchedule(
    calendarContext: "...",  // required — The name of the calendar context the schedule is read in, which must be one the Launcher declares
    recurrencePattern: new RecurrencePattern(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherSchedule>(json);
```

- [RecurrencePattern](RecurrencePattern.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

