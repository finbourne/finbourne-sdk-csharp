# Finbourne.Sdk.Lusid.Model.TaxReturnVintage

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PeriodId** | **string** | Optional | The label of the period the amount falls into. |
| **Start** | **DateTimeOffset** | Optional | The first day of the period, inclusive. |
| **End** | **DateTimeOffset** | Optional | The last day of the period, inclusive. |
| **DeemedGains** | **decimal** | Optional | The deemed gains arising at the end of the period. |
| **DeemedLosses** | **decimal** | Optional | The deemed losses arising at the end of the period. |
| **NetAmount** | **decimal** | Optional | The net deemed amount, gains less losses. |
| **CarryBackReduction** | **decimal** | Optional | The reduction to the net amount from losses carried back from later periods. |
| **SpreadAmount** | **decimal** | Optional | The net amount after carry-back that is spread over seven periods. |
| **Outstanding** | **decimal** | Optional | The amount of the spread that has not yet been brought into charge. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnVintage(
    periodId: "...",  // optional — The label of the period the amount falls into.
    start: DateTimeOffset.Now,  // optional — The first day of the period, inclusive.
    end: DateTimeOffset.Now,  // optional — The last day of the period, inclusive.
    deemedGains: 0.0d,  // optional — The deemed gains arising at the end of the period.
    deemedLosses: 0.0d,  // optional — The deemed losses arising at the end of the period.
    netAmount: 0.0d,  // optional — The net deemed amount, gains less losses.
    carryBackReduction: 0.0d,  // optional — The reduction to the net amount from losses carried back from later periods.
    spreadAmount: 0.0d,  // optional — The net amount after carry-back that is spread over seven periods.
    outstanding: 0.0d  // optional — The amount of the spread that has not yet been brought into charge.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnVintage>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

