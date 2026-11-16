# Finbourne.Sdk.Lusid.Model.AccruedFeeLine

A management fee accrued to one partner that the run left to its accrual rather than pooling.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Optional | The partner the fee was accrued to, when the accrual names one. |
| **Amount** | **decimal** | Required | The fee accrued to the partner, as the journal debits it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccruedFeeLine(
    investorRecordId: "...",  // optional — The partner the fee was accrued to, when the accrual names one.
    amount: 0.0d  // required — The fee accrued to the partner, as the journal debits it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccruedFeeLine>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

