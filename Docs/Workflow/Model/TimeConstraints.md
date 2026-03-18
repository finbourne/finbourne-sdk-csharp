# Finbourne.Sdk.Workflow.Model.TimeConstraints

Time constraints for a Recurrence Pattern
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **string** | Required | Start date of the Recurrence Pattern e.g. 2025-12-25 |
| **EndDate** | **string** | Optional | Optional end date of the Recurrence Pattern e.g. 2025-12-31 |
| **TimesOfDay** | [List&lt;TimeOfDay&gt;](TimeOfDay.md) | Required | Times of the day to run the Recurrence Pattern |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TimeConstraints(
    startDate: "...",  // required — Start date of the Recurrence Pattern e.g. 2025-12-25
    endDate: "...",  // optional — Optional end date of the Recurrence Pattern e.g. 2025-12-31
    timesOfDay: new List<TimeOfDay>()  // required — Times of the day to run the Recurrence Pattern
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TimeConstraints>(json);
```

- [TimeOfDay](TimeOfDay.md) — used in `TimesOfDay`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

