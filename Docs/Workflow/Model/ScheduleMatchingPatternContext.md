# Finbourne.Sdk.Workflow.Model.ScheduleMatchingPatternContext

Context for a Schedule Matching Pattern
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarTimeZone** | **string** | Required | The time zone to use. A TZ Identifier e.g. \&quot;Europe/London\&quot; |
| **HolidayCalendars** | [List&lt;CalendarReference&gt;](CalendarReference.md) | Optional | References to any Holiday Calendars to use |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ScheduleMatchingPatternContext(
    varTimeZone: "...",  // required — The time zone to use. A TZ Identifier e.g. \&quot;Europe/London\&quot;
    holidayCalendars: new List<CalendarReference>()  // optional — References to any Holiday Calendars to use
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScheduleMatchingPatternContext>(json);
```

- [CalendarReference](CalendarReference.md) — used in `HolidayCalendars`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

