# Finbourne.Sdk.Workflow.Model.ScheduleMatchingPattern

The Schedule Matching Pattern to trigger on
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Context** | [ScheduleMatchingPatternContext](ScheduleMatchingPatternContext.md) | Required | *No description available.* |
| **RecurrencePattern** | [RecurrencePattern](RecurrencePattern.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ScheduleMatchingPattern(
    context: new ScheduleMatchingPatternContext(...),  // required
    recurrencePattern: new RecurrencePattern(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScheduleMatchingPattern>(json);
```


## Related Models

- [ScheduleMatchingPatternContext](ScheduleMatchingPatternContext.md)
- [RecurrencePattern](RecurrencePattern.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

