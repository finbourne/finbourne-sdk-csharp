# Finbourne.Sdk.Workflow.Model.DateAdjustment

A date adjustment to apply to the scheduled time of an EventHandler with a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DeltaDays** | **int** | Required | The delta to apply to the date part of the scheduled time, in days |
| **BusinessDayAdjustment** | **string** | Required | The Business Day Adjustment |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new DateAdjustment(
    deltaDays: 0,  // required — The delta to apply to the date part of the scheduled time, in days
    businessDayAdjustment: "..."  // required — The Business Day Adjustment
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DateAdjustment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

