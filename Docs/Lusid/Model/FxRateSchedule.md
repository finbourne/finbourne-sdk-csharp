# Finbourne.Sdk.Lusid.Model.FxRateSchedule

Schedule to define fx conversion of cashflows on complex bonds. If an fx schedule is defined then  on payment schedule generation the coupon and principal payoffs will be wrapped in an fx rate payoff method.  Either the fx rate is predefined (fixed) or relies on fx resets (floating).  Used in representation of dual currency bond.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **FxConversionTypes** | **List&lt;string&gt;** | Optional | List of flags to indicate if coupon payments, principal payments or both are converted |
| **Rate** | **decimal** | Optional | FxRate used to convert payments. Assumed to be in units of the ToCurrency so conversion is paymentAmount x fxRate |
| **ToCurrency** | **string** | Optional | Currency that payments are converted to |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.FxRateSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxRateSchedule(
    flowConventions: new FlowConventions(...),  // optional
    fxConversionTypes: ,  // optional — List of flags to indicate if coupon payments, principal payments or both are converted
    rate: 0.0d,  // optional — FxRate used to convert payments. Assumed to be in units of the ToCurrency so conversion is paymentAmount x fxRate
    toCurrency: "...",  // optional — Currency that payments are converted to
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxRateSchedule>(json);
```



- [FlowConventions](FlowConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

