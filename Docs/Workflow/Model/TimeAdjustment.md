# Finbourne.Sdk.Workflow.Model.TimeAdjustment

A time adjustment to apply to the scheduled time of an EventHandler with a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SetTo** | [SpecifiedTime](SpecifiedTime.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TimeAdjustment(
    setTo: new SpecifiedTime(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TimeAdjustment>(json);
```


## Related Models

- [SpecifiedTime](SpecifiedTime.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

