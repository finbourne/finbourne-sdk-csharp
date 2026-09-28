# Finbourne.Sdk.Workflow.Model.DateTimeAdjustment

A change applied to the date and the time of a source value, in a named calendar context.              At least one of Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.DateTimeAdjustment.DateAdjustment or Finbourne.Workflow.WebApi.Common.Dto.Json.Launchers.DateTimeAdjustment.TimeAdjustment must be given
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalendarContext** | **string** | Optional | The name of the calendar context this change happens in, which must be one the Launcher declares. When it is left out a Schedule Launcher uses the context of its schedule |
| **DateAdjustment** | [DateAdjustment](DateAdjustment.md) | Optional | *No description available.* |
| **TimeAdjustment** | [TimeAdjustment](TimeAdjustment.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new DateTimeAdjustment(
    calendarContext: "...",  // optional — The name of the calendar context this change happens in, which must be one the Launcher declares. When it is left out a Schedule Launcher uses the context of its schedule
    dateAdjustment: new DateAdjustment(...),  // optional
    timeAdjustment: new TimeAdjustment(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateTimeAdjustment>(json);
```

- [DateAdjustment](DateAdjustment.md)
- [TimeAdjustment](TimeAdjustment.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

