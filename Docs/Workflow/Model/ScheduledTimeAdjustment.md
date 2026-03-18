# Finbourne.Sdk.Workflow.Model.ScheduledTimeAdjustment

Represents an adjustment to the scheduled time of an EventHandler. Only relevant for EventHandlers with a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DateAdjustment** | [DateAdjustment](DateAdjustment.md) | Required | *No description available.* |
| **TimeAdjustment** | [TimeAdjustment](TimeAdjustment.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ScheduledTimeAdjustment(
    dateAdjustment: new DateAdjustment(...),  // required
    timeAdjustment: new TimeAdjustment(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScheduledTimeAdjustment>(json);
```


## Related Models

- [DateAdjustment](DateAdjustment.md)
- [TimeAdjustment](TimeAdjustment.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

