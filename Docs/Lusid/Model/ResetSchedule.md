# Finbourne.Sdk.Lusid.Model.ResetSchedule

The schedule on which the price return of the asset leg of a total return swap is observed and exchanged.  Each reset period pays the change in the asset's price over the period, sourced from quoted market data.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Conventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **FirstResetDate** | **DateTimeOffset?** | Optional | The date of the first price reset. Optional; when absent the reset dates are rolled forward from the swap start date. |
| **Frequency** | **string** | Required | The frequency at which the asset price is reset and the price return is exchanged, e.g. 3M. |
| **LastResetDate** | **DateTimeOffset?** | Optional | The date of the last price reset. Optional; when absent the reset dates are rolled forward until the swap maturity date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResetSchedule(
    conventions: new FlowConventions(...),  // optional
    firstResetDate: DateTimeOffset.Now,  // optional — The date of the first price reset. Optional; when absent the reset dates are rolled forward from the swap start date.
    frequency: "...",  // required — The frequency at which the asset price is reset and the price return is exchanged, e.g. 3M.
    lastResetDate: DateTimeOffset.Now  // optional — The date of the last price reset. Optional; when absent the reset dates are rolled forward until the swap maturity date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResetSchedule>(json);
```


## Related Models

- [FlowConventions](FlowConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

