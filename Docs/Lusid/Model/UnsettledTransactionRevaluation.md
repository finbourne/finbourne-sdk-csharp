# Finbourne.Sdk.Lusid.Model.UnsettledTransactionRevaluation

The transaction's total consideration in base currency, both at the rate it was booked at and revalued at the  valuation point's FX rate. Rates and amounts are null when they could not be resolved; Problems explains why.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LocalCurrency** | **string** | Optional | The settlement currency of the transaction (the &#39;local&#39; currency for revaluation purposes). |
| **LocalAmount** | **decimal** | Optional | The total consideration in the settlement currency, as booked. |
| **BaseCurrency** | **string** | Optional | The fund&#39;s base currency. |
| **BaseFxRate** | **decimal?** | Optional | The FX rate from settlement currency to base currency at the time the transaction was booked. Null when no booked rate was recorded. |
| **BaseAmount** | **decimal?** | Optional | The total consideration in base currency at the booked FX rate. Null when the booked rate is unavailable. |
| **RevaluationFxRate** | **decimal?** | Optional | The FX rate from settlement currency to base currency at the valuation point&#39;s effective date. Null when the rate could not be resolved. |
| **RevaluedBaseAmount** | **decimal?** | Optional | The total consideration in base currency revalued at the valuation point&#39;s FX rate. Null when the revaluation rate is unavailable. |
| **RevaluationFxRateEffectiveAt** | **DateTimeOffset?** | Optional | The effective date of the quote used for the revaluation FX rate. Null for same-currency transactions or when the rate is missing. |
| **Status** | **string** | Optional | Whether revaluation succeeded (Revalued), was not needed (SameCurrency), or failed due to a missing FX rate (MissingFxRate). |
| **Problems** | [List&lt;RevaluationProblem&gt;](RevaluationProblem.md) | Optional | Reasons why any of the amounts could not be populated. Empty when revaluation succeeded. |
| **CounterLeg** | [UnsettledTransactionCounterLegRevaluation](UnsettledTransactionCounterLegRevaluation.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnsettledTransactionRevaluation(
    localCurrency: "...",  // optional — The settlement currency of the transaction (the &#39;local&#39; currency for revaluation purposes).
    localAmount: 0.0d,  // optional — The total consideration in the settlement currency, as booked.
    baseCurrency: "...",  // optional — The fund&#39;s base currency.
    baseFxRate: 0.0d,  // optional — The FX rate from settlement currency to base currency at the time the transaction was booked. Null when no booked rate was recorded.
    baseAmount: 0.0d,  // optional — The total consideration in base currency at the booked FX rate. Null when the booked rate is unavailable.
    revaluationFxRate: 0.0d,  // optional — The FX rate from settlement currency to base currency at the valuation point&#39;s effective date. Null when the rate could not be resolved.
    revaluedBaseAmount: 0.0d,  // optional — The total consideration in base currency revalued at the valuation point&#39;s FX rate. Null when the revaluation rate is unavailable.
    revaluationFxRateEffectiveAt: DateTimeOffset.Now,  // optional — The effective date of the quote used for the revaluation FX rate. Null for same-currency transactions or when the rate is missing.
    status: "...",  // optional — Whether revaluation succeeded (Revalued), was not needed (SameCurrency), or failed due to a missing FX rate (MissingFxRate).
    problems: new List<RevaluationProblem>(),  // optional — Reasons why any of the amounts could not be populated. Empty when revaluation succeeded.
    counterLeg: new UnsettledTransactionCounterLegRevaluation(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnsettledTransactionRevaluation>(json);
```

- [RevaluationProblem](RevaluationProblem.md) — used in `Problems`
- [UnsettledTransactionCounterLegRevaluation](UnsettledTransactionCounterLegRevaluation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

