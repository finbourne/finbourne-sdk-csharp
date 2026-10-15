# Finbourne.Sdk.Lusid.Model.ProcessingGroupSchedule

Specification of the dates on which a Processing Group is executed: a date range plus  tenor / roll / business-day conventions and holiday calendars that generate the schedule,  or an explicit override set of dates. Modelled on the valuation schedule shape, without the  bitemporal timeline fields.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveFrom** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The start of the date range over which the schedule is generated. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The end of the date range over which the schedule is generated. |
| **Tenor** | **string** | Optional | Tenor, e.g. \&quot;1D\&quot;, \&quot;1M\&quot;, used to generate the date schedule between EffectiveFrom and EffectiveAt. |
| **RollConvention** | **string** | Optional | When Tenor is \&quot;1M\&quot; or longer, the rule used to generate the date schedule, e.g. \&quot;EndOfMonth\&quot; or \&quot;1\&quot;. |
| **HolidayCalendars** | **List&lt;string&gt;** | Optional | The holiday calendar(s), by name, used when determining business days for the schedule. |
| **ScheduleDates** | **List&lt;string&gt;** | Optional | If given, the exact set of dates on which to execute. Overrides the generated schedule. |
| **BusinessDayConvention** | **string** | Optional | When Tenor is not \&quot;1D\&quot;, the convention (e.g. \&quot;MF\&quot;) used to roll dates that land on non-business days. |
| **VarTimeZone** | **string** | Optional | The IANA approved time zone (tzdb id, e.g. \&quot;Europe/London\&quot;) the schedule is expressed in.  Informational for consumers of the schedule: the generated schedule dates are calendar dates  and are not adjusted by this time zone. Optional. |
| **BusinessDayOffset** | **int?** | Optional | If given, the number of good business days (per the holiday calendars) added to each generated  date. Can be negative. For example, the 10th business day of each month is a \&quot;1M\&quot; tenor with an  \&quot;EndOfMonth\&quot; roll convention and a business day offset of 10. Cannot be combined with ScheduleDates. |
| **DateExceptions** | **List&lt;string&gt;** | Optional | Dates, in yyyy-MM-dd format, on which the Processing Group does not run. These are removed  from the generated schedule after all other conventions and offsets have been applied. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ProcessingGroupSchedule(
    effectiveFrom: new DateTimeOrCutLabel(...),  // optional — The start of the date range over which the schedule is generated.
    effectiveAt: new DateTimeOrCutLabel(...),  // optional — The end of the date range over which the schedule is generated.
    tenor: "...",  // optional — Tenor, e.g. \&quot;1D\&quot;, \&quot;1M\&quot;, used to generate the date schedule between EffectiveFrom and EffectiveAt.
    rollConvention: "...",  // optional — When Tenor is \&quot;1M\&quot; or longer, the rule used to generate the date schedule, e.g. \&quot;EndOfMonth\&quot; or \&quot;1\&quot;.
    holidayCalendars: ,  // optional — The holiday calendar(s), by name, used when determining business days for the schedule.
    scheduleDates: ,  // optional — If given, the exact set of dates on which to execute. Overrides the generated schedule.
    businessDayConvention: "...",  // optional — When Tenor is not \&quot;1D\&quot;, the convention (e.g. \&quot;MF\&quot;) used to roll dates that land on non-business days.
    varTimeZone: "...",  // optional — The IANA approved time zone (tzdb id, e.g. \&quot;Europe/London\&quot;) the schedule is expressed in.  Informational for consumers of the schedule: the generated schedule dates are calendar dates  and are not adjusted by this time zone. Optional.
    businessDayOffset: 0,  // optional — If given, the number of good business days (per the holiday calendars) added to each generated  date. Can be negative. For example, the 10th business day of each month is a \&quot;1M\&quot; tenor with an  \&quot;EndOfMonth\&quot; roll convention and a business day offset of 10. Cannot be combined with ScheduleDates.
    dateExceptions:   // optional — Dates, in yyyy-MM-dd format, on which the Processing Group does not run. These are removed  from the generated schedule after all other conventions and offsets have been applied.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessingGroupSchedule>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveFrom`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

