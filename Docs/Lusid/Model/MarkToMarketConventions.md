# Finbourne.Sdk.Lusid.Model.MarkToMarketConventions

A set of conventions for mark to market. Mark to market is a method   that values financial instruments based on current market prices,   reflecting their current value, rather than historical cost.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalendarCode** | **string** | Optional | The calendar to use when generating mark to market cashflows and events. |
| **HourOffsetTenor** | **string** | Optional | The hour tenor component of the time offset against the maturity date.  This is an optional field, if a value is provided it must be a positive value between &#39;0hour&#39; and &#39;23hour&#39;. |
| **MinuteOffsetTenor** | **string** | Optional | The minute tenor component of the time offset against the maturity date.  This is an optional field, if a value is provided it must be a positive value between &#39;0min&#39; and &#39;59min&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarkToMarketConventions(
    calendarCode: "...",  // optional — The calendar to use when generating mark to market cashflows and events.
    hourOffsetTenor: "...",  // optional — The hour tenor component of the time offset against the maturity date.  This is an optional field, if a value is provided it must be a positive value between &#39;0hour&#39; and &#39;23hour&#39;.
    minuteOffsetTenor: "..."  // optional — The minute tenor component of the time offset against the maturity date.  This is an optional field, if a value is provided it must be a positive value between &#39;0min&#39; and &#39;59min&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarkToMarketConventions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

