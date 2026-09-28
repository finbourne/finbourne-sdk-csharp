# Finbourne.Sdk.Workflow.Model.ScheduleTaskFieldMapping

How a Schedule Launcher fills one field of the root task from the instant the schedule fired
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MapFrom** | **string** | Required | The value the field is taken from. One of - ScheduledTime |
| **DateTimeAdjustment** | [DateTimeAdjustment](DateTimeAdjustment.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ScheduleTaskFieldMapping(
    mapFrom: "...",  // required — The value the field is taken from. One of - ScheduledTime
    dateTimeAdjustment: new DateTimeAdjustment(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScheduleTaskFieldMapping>(json);
```

- [DateTimeAdjustment](DateTimeAdjustment.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

