# Finbourne.Sdk.Workflow.Model.RecurrencePattern

The Recurrence Pattern
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TimeConstraints** | [TimeConstraints](TimeConstraints.md) | Required | *No description available.* |
| **DateRegularity** | [DateRegularity](DateRegularity.md) | Required | *No description available.* |
| **BusinessDayAdjustment** | **string** | Required | The Business Day Adjustment. One of None, Previous, Following, ModifiedPrevious, ModifiedFollowing, HalfMonthModifiedFollowing, Nearest |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new RecurrencePattern(
    timeConstraints: new TimeConstraints(...),  // required
    dateRegularity: new DateRegularity(...),  // required
    businessDayAdjustment: "..."  // required — The Business Day Adjustment. One of None, Previous, Following, ModifiedPrevious, ModifiedFollowing, HalfMonthModifiedFollowing, Nearest
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecurrencePattern>(json);
```


## Related Models

- [TimeConstraints](TimeConstraints.md)
- [DateRegularity](DateRegularity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

