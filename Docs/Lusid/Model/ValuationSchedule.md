# Finbourne.Sdk.Lusid.Model.ValuationSchedule

Specification object for the valuation schedule, how do we determine which days we wish to perform a valuation upon.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveFrom** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | If present, the EffectiveFrom and EffectiveAt dates are interpreted as a range of dates for which to perform a valuation.  In this case, valuation is calculated for the portfolio(s) for each business day in the given range. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The market data time, i.e. the time to run the valuation request effective of. |
| **Tenor** | **string** | Optional | Tenor, e.g \&quot;1D\&quot;, \&quot;1M\&quot; to be used in generating the date schedule when effectiveFrom and effectiveAt are both given and are not the same. |
| **RollConvention** | **string** | Optional | When Tenor is given and is \&quot;1M\&quot; or longer, this specifies the rule which should be used to generate the date schedule.    For example, \&quot;EndOfMonth\&quot; to generate end of month dates, or \&quot;1\&quot; to specify the first day of the applicable month. |
| **HolidayCalendars** | **List&lt;string&gt;** | Optional | The holiday calendar(s) that should be used in determining the date schedule.  Holiday calendar(s) are supplied by their names, for example, \&quot;CoppClark\&quot;.   Note that when the calendars are not available (e.g. when the user has insufficient permissions),   a recipe setting will be used to determine whether the whole batch should then fail or whether the calendar not being available should simply be ignored. |
| **ValuationDateTimes** | **List&lt;string&gt;** | Optional | If given, this is the exact set of dates on which to perform a valuation. This will replace/override all other specified values if given. |
| **BusinessDayConvention** | **string** | Optional | When Tenor is given and is not equal to \&quot;1D\&quot;, there may be cases where \&quot;date + tenor\&quot; land on non-business days around month end.  In that case, the BusinessDayConvention, e.g. modified following \&quot;MF\&quot; would be applied to determine the next GBD. |
| **TimelineId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ClosedPeriodId** | **string** | Optional | Unique identifier for a closed period within a given timeline. If this field is specified, the TimelineId  field must also be specified. If given, this field defines the effective date of the request as the  EffectiveEnd of the given closed period. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationSchedule(
    effectiveFrom: new DateTimeOrCutLabel(...),  // optional — If present, the EffectiveFrom and EffectiveAt dates are interpreted as a range of dates for which to perform a valuation.  In this case, valuation is calculated for the portfolio(s) for each business day in the given range.
    effectiveAt: new DateTimeOrCutLabel(...),  // optional — The market data time, i.e. the time to run the valuation request effective of.
    tenor: "...",  // optional — Tenor, e.g \&quot;1D\&quot;, \&quot;1M\&quot; to be used in generating the date schedule when effectiveFrom and effectiveAt are both given and are not the same.
    rollConvention: "...",  // optional — When Tenor is given and is \&quot;1M\&quot; or longer, this specifies the rule which should be used to generate the date schedule.    For example, \&quot;EndOfMonth\&quot; to generate end of month dates, or \&quot;1\&quot; to specify the first day of the applicable month.
    holidayCalendars: ,  // optional — The holiday calendar(s) that should be used in determining the date schedule.  Holiday calendar(s) are supplied by their names, for example, \&quot;CoppClark\&quot;.   Note that when the calendars are not available (e.g. when the user has insufficient permissions),   a recipe setting will be used to determine whether the whole batch should then fail or whether the calendar not being available should simply be ignored.
    valuationDateTimes: ,  // optional — If given, this is the exact set of dates on which to perform a valuation. This will replace/override all other specified values if given.
    businessDayConvention: "...",  // optional — When Tenor is given and is not equal to \&quot;1D\&quot;, there may be cases where \&quot;date + tenor\&quot; land on non-business days around month end.  In that case, the BusinessDayConvention, e.g. modified following \&quot;MF\&quot; would be applied to determine the next GBD.
    timelineId: new ResourceId(...),  // optional
    closedPeriodId: "..."  // optional — Unique identifier for a closed period within a given timeline. If this field is specified, the TimelineId  field must also be specified. If given, this field defines the effective date of the request as the  EffectiveEnd of the given closed period.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationSchedule>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveFrom`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

