# Finbourne.Sdk.Workflow.Model.CalendarContext

A named time zone and set of holiday calendars.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name the schedule and the date and time adjustments use to name this context |
| **VarTimeZone** | **string** | Required | The time zone to use. A TZ identifier, for example \&quot;Europe/London\&quot; |
| **HolidayCalendars** | [List&lt;CalendarReference&gt;](CalendarReference.md) | Optional | The holiday calendars that decide which dates are business days in this context |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CalendarContext(
    name: "...",  // required — The name the schedule and the date and time adjustments use to name this context
    varTimeZone: "...",  // required — The time zone to use. A TZ identifier, for example \&quot;Europe/London\&quot;
    holidayCalendars: new List<CalendarReference>()  // optional — The holiday calendars that decide which dates are business days in this context
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CalendarContext>(json);
```

- [CalendarReference](CalendarReference.md) — used in `HolidayCalendars`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

