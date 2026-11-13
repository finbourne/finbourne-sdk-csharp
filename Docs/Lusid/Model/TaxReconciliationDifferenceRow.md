# Finbourne.Sdk.Lusid.Model.TaxReconciliationDifferenceRow

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingId** | **string** | Optional | The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier. |
| **InstrumentId** | **string** | Optional | The LUSID unique identifier of the instrument. |
| **InstrumentName** | **string** | Optional | The name of the instrument. |
| **Category** | **string** | Optional | The reconciliation category. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest. |
| **ComparedAmount** | **decimal** | Optional | The amount on the side being reconciled from. |
| **TaxAmount** | **decimal** | Optional | The amount on the tax side. |
| **Difference** | **decimal** | Optional | The difference between the two sides. |
| **Explanation** | **string** | Optional | The explanation of the difference. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReconciliationDifferenceRow(
    holdingId: "...",  // optional — The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier.
    instrumentId: "...",  // optional — The LUSID unique identifier of the instrument.
    instrumentName: "...",  // optional — The name of the instrument.
    category: "...",  // optional — The reconciliation category. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest.
    comparedAmount: 0.0d,  // optional — The amount on the side being reconciled from.
    taxAmount: 0.0d,  // optional — The amount on the tax side.
    difference: 0.0d,  // optional — The difference between the two sides.
    explanation: "..."  // optional — The explanation of the difference.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReconciliationDifferenceRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

