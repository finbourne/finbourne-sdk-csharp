# Finbourne.Sdk.Lusid.Model.UnsettledTransactionCounterLegRevaluation

The receiving (counter) leg of an FX forward revalued into the fund's base currency at the valuation point's  FX rates. Populated only for FX forward transactions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LocalCurrency** | **string** | Optional | The currency of the FX forward&#39;s receiving (counter) leg. |
| **LocalAmount** | **decimal** | Optional | The amount of the receiving leg in its own currency. |
| **BaseCurrency** | **string** | Optional | The fund&#39;s base currency. |
| **BookedBaseAmount** | **decimal?** | Optional | The receiving leg amount in base currency at the rate booked on the transaction. Null when no booked rate was recorded. |
| **RevaluationFxRate** | **decimal?** | Optional | The FX rate from the counter-leg currency to base currency at the valuation point&#39;s effective date. Null when the rate could not be resolved. |
| **RevaluedBaseAmount** | **decimal?** | Optional | The receiving leg amount in base currency revalued at the valuation point&#39;s FX rate. Null when the revaluation rate is unavailable. |
| **RevaluationFxRateEffectiveAt** | **DateTimeOffset?** | Optional | The effective date of the quote used for the counter-leg revaluation FX rate. Null for same-currency legs or when the rate is missing. |
| **Status** | **string** | Optional | Whether counter-leg revaluation succeeded (Revalued), was not needed (SameCurrency), or failed due to a missing FX rate (MissingFxRate). |
| **Problems** | [List&lt;RevaluationProblem&gt;](RevaluationProblem.md) | Optional | Reasons why any counter-leg amounts could not be populated. Empty when revaluation succeeded. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnsettledTransactionCounterLegRevaluation(
    localCurrency: "...",  // optional — The currency of the FX forward&#39;s receiving (counter) leg.
    localAmount: 0.0d,  // optional — The amount of the receiving leg in its own currency.
    baseCurrency: "...",  // optional — The fund&#39;s base currency.
    bookedBaseAmount: 0.0d,  // optional — The receiving leg amount in base currency at the rate booked on the transaction. Null when no booked rate was recorded.
    revaluationFxRate: 0.0d,  // optional — The FX rate from the counter-leg currency to base currency at the valuation point&#39;s effective date. Null when the rate could not be resolved.
    revaluedBaseAmount: 0.0d,  // optional — The receiving leg amount in base currency revalued at the valuation point&#39;s FX rate. Null when the revaluation rate is unavailable.
    revaluationFxRateEffectiveAt: DateTimeOffset.Now,  // optional — The effective date of the quote used for the counter-leg revaluation FX rate. Null for same-currency legs or when the rate is missing.
    status: "...",  // optional — Whether counter-leg revaluation succeeded (Revalued), was not needed (SameCurrency), or failed due to a missing FX rate (MissingFxRate).
    problems: new List<RevaluationProblem>()  // optional — Reasons why any counter-leg amounts could not be populated. Empty when revaluation succeeded.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnsettledTransactionCounterLegRevaluation>(json);
```

- [RevaluationProblem](RevaluationProblem.md) — used in `Problems`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

