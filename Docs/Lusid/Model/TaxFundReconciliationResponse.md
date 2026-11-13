# Finbourne.Sdk.Lusid.Model.TaxFundReconciliationResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Period** | [TaxAccountingPeriod](TaxAccountingPeriod.md) | Optional | *No description available.* |
| **CompanyTotal** | **decimal** | Optional | The company-level total of lines A, D and LR. |
| **SumOfFundProxies** | **decimal** | Optional | The sum of the member funds&#39; notional totals. |
| **Differences** | [List&lt;TaxReconciliationDifferenceRow&gt;](TaxReconciliationDifferenceRow.md) | Optional | The explained differences between the two sides, by holding. |
| **Unexplained** | **decimal** | Optional | The part of the difference not explained by any category. Nil when the reconciliation is complete. |
| **CompanyLineD** | **decimal** | Optional | Line D at company level. |
| **FundsLineD** | **decimal** | Optional | The sum of line D across the member funds. |
| **CompanyLineLR** | **decimal** | Optional | Line LR at company level. |
| **FundsLineLR** | **decimal** | Optional | The sum of line LR across the member funds. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxFundReconciliationResponse(
    fundId: new ResourceId(...),  // optional
    period: new TaxAccountingPeriod(...),  // optional
    companyTotal: 0.0d,  // optional — The company-level total of lines A, D and LR.
    sumOfFundProxies: 0.0d,  // optional — The sum of the member funds&#39; notional totals.
    differences: new List<TaxReconciliationDifferenceRow>(),  // optional — The explained differences between the two sides, by holding.
    unexplained: 0.0d,  // optional — The part of the difference not explained by any category. Nil when the reconciliation is complete.
    companyLineD: 0.0d,  // optional — Line D at company level.
    fundsLineD: 0.0d,  // optional — The sum of line D across the member funds.
    companyLineLR: 0.0d,  // optional — Line LR at company level.
    fundsLineLR: 0.0d  // optional — The sum of line LR across the member funds.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxFundReconciliationResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxAccountingPeriod](TaxAccountingPeriod.md)
- [TaxReconciliationDifferenceRow](TaxReconciliationDifferenceRow.md) — used in `Differences`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

