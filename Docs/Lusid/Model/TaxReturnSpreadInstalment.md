# Finbourne.Sdk.Lusid.Model.TaxReturnSpreadInstalment

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourcePeriodId** | **string** | Optional | The label of the period whose deemed disposal is being spread. |
| **PeriodId** | **string** | Optional | The label of the period the amount falls into. |
| **Fraction** | **decimal** | Optional | The fraction of the source period&#39;s spread amount that falls into the period. |
| **Amount** | **decimal** | Optional | The amount, in pounds. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnSpreadInstalment(
    sourcePeriodId: "...",  // optional — The label of the period whose deemed disposal is being spread.
    periodId: "...",  // optional — The label of the period the amount falls into.
    fraction: 0.0d,  // optional — The fraction of the source period&#39;s spread amount that falls into the period.
    amount: 0.0d  // optional — The amount, in pounds.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnSpreadInstalment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

