# Finbourne.Sdk.Lusid.Model.UpsertTaxTreatmentOverrideRequest

Pins an instrument to a treatment leaf in place of the system-derived one.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Treatment** | **string** | Required | The treatment leaf to pin the instrument to, replacing the system-derived one. Available values: OutsideBlagab, LoanRelationship, IndexLinkedGilt, PrivateEquity, RealEstate, FinancialFuture, PooledDerivative, DerivativeProfitAndLoss, NonTransparentScheme, BondFund, TransparentScheme, StandardEquity, Exempt. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective date the override applies from. Defaults to the start of time if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertTaxTreatmentOverrideRequest(
    treatment: "...",  // required — The treatment leaf to pin the instrument to, replacing the system-derived one. Available values: OutsideBlagab, LoanRelationship, IndexLinkedGilt, PrivateEquity, RealEstate, FinancialFuture, PooledDerivative, DerivativeProfitAndLoss, NonTransparentScheme, BondFund, TransparentScheme, StandardEquity, Exempt.
    effectiveAt: DateTimeOffset.Now  // optional — The effective date the override applies from. Defaults to the start of time if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertTaxTreatmentOverrideRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

