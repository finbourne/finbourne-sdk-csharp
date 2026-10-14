# Finbourne.Sdk.Lusid.Model.LoanFacilityTaxLotAllocation

Contract-level state for a single tax lot on a single contract. These values live on the contract holding.                Each allocation names its own contract rather than being grouped under one, so the event carries a flat  list. A tax lot holding a balance on two contracts appears twice, once per contract.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ContractDetails** | [ContractDetails](ContractDetails.md) | Required | *No description available.* |
| **TaxLotId** | **string** | Required | The tax lot being set, identified by the transaction id of the trade that opened it. |
| **Balance** | **decimal** | Required | The desired settled balance for this tax lot on this contract, in the contract&#39;s own currency. This  replaces the pro-rata balance that the opening trade derived from the global facility state, which is  how a non-pro-rata position is expressed. |
| **BalanceInFacilityCcy** | **decimal?** | Optional | The desired balance expressed in the facility currency. Required when the contract currency differs  from the facility currency, and defaults to Balance otherwise. |
| **AccruedInterest** | **decimal?** | Optional | Interest accrued on this tax lot&#39;s balance on this contract, as at the start of the event&#39;s date, in  the contract&#39;s own currency. Distinct from the facility&#39;s own accrual on its undrawn amount - the two  are summed to give the accrued interest reported against the holding.                Omit it and the lot&#39;s accrual is left as it is, so a migrated lot accrues from its own trade date. |
| **PikAccruedInterest** | **decimal?** | Optional | Payment-in-kind interest accrued on this tax lot, as at the start of the event&#39;s date, for a contract  carrying a PIK schedule. Tracked separately from cash-settled accrual and never derived. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LoanFacilityTaxLotAllocation(
    contractDetails: new ContractDetails(...),  // required
    taxLotId: "...",  // required — The tax lot being set, identified by the transaction id of the trade that opened it.
    balance: 0.0d,  // required — The desired settled balance for this tax lot on this contract, in the contract&#39;s own currency. This  replaces the pro-rata balance that the opening trade derived from the global facility state, which is  how a non-pro-rata position is expressed.
    balanceInFacilityCcy: 0.0d,  // optional — The desired balance expressed in the facility currency. Required when the contract currency differs  from the facility currency, and defaults to Balance otherwise.
    accruedInterest: 0.0d,  // optional — Interest accrued on this tax lot&#39;s balance on this contract, as at the start of the event&#39;s date, in  the contract&#39;s own currency. Distinct from the facility&#39;s own accrual on its undrawn amount - the two  are summed to give the accrued interest reported against the holding.                Omit it and the lot&#39;s accrual is left as it is, so a migrated lot accrues from its own trade date.
    pikAccruedInterest: 0.0d  // optional — Payment-in-kind interest accrued on this tax lot, as at the start of the event&#39;s date, for a contract  carrying a PIK schedule. Tracked separately from cash-settled accrual and never derived.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LoanFacilityTaxLotAllocation>(json);
```


## Related Models

- [ContractDetails](ContractDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

