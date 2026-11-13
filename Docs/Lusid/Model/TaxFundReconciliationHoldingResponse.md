# Finbourne.Sdk.Lusid.Model.TaxFundReconciliationHoldingResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Period** | [TaxAccountingPeriod](TaxAccountingPeriod.md) | Optional | *No description available.* |
| **HoldingId** | **string** | Optional | The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier. |
| **InstrumentId** | **string** | Optional | The LUSID unique identifier of the instrument. |
| **InstrumentName** | **string** | Optional | The name of the instrument. |
| **CompanyAmount** | **decimal** | Optional | The company-level amount for the holding. |
| **FundProxies** | [List&lt;TaxFundReconciliationProxyRow&gt;](TaxFundReconciliationProxyRow.md) | Optional | The member funds&#39; notional figures for the holding. |
| **Difference** | **decimal** | Optional | The difference between the two sides. |
| **Category** | **string** | Optional | The reconciliation category of the difference, when there is one. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest. |
| **Explanation** | **string** | Optional | The explanation of the difference. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxFundReconciliationHoldingResponse(
    fundId: new ResourceId(...),  // optional
    period: new TaxAccountingPeriod(...),  // optional
    holdingId: "...",  // optional — The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier.
    instrumentId: "...",  // optional — The LUSID unique identifier of the instrument.
    instrumentName: "...",  // optional — The name of the instrument.
    companyAmount: 0.0d,  // optional — The company-level amount for the holding.
    fundProxies: new List<TaxFundReconciliationProxyRow>(),  // optional — The member funds&#39; notional figures for the holding.
    difference: 0.0d,  // optional — The difference between the two sides.
    category: "...",  // optional — The reconciliation category of the difference, when there is one. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest.
    explanation: "..."  // optional — The explanation of the difference.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxFundReconciliationHoldingResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxAccountingPeriod](TaxAccountingPeriod.md)
- [TaxFundReconciliationProxyRow](TaxFundReconciliationProxyRow.md) — used in `FundProxies`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

