# Finbourne.Sdk.Lusid.Model.GlobalLoanFacilityContractState

The desired global state of a single FlexibleLoan contract. Balances are global - across all investors -  rather than investor specific.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ContractDetails** | [ContractDetails](ContractDetails.md) | Required | *No description available.* |
| **Balance** | **decimal** | Required | The desired global balance for this contract, in the contract&#39;s own currency. Must be non-negative. |
| **BalanceInFacilityCcy** | **decimal?** | Optional | The desired global balance expressed in the facility currency. Required when the contract currency  differs from the facility currency, and defaults to Balance otherwise. |
| **AgencyFxRate** | **decimal?** | Optional | The agency FX rate converting contract currency to facility currency. Required when the contract  currency differs from the facility currency. When omitted it is derived from the two balances where  possible, and otherwise defaults to 1. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GlobalLoanFacilityContractState(
    contractDetails: new ContractDetails(...),  // required
    balance: 0.0d,  // required — The desired global balance for this contract, in the contract&#39;s own currency. Must be non-negative.
    balanceInFacilityCcy: 0.0d,  // optional — The desired global balance expressed in the facility currency. Required when the contract currency  differs from the facility currency, and defaults to Balance otherwise.
    agencyFxRate: 0.0d  // optional — The agency FX rate converting contract currency to facility currency. Required when the contract  currency differs from the facility currency. When omitted it is derived from the two balances where  possible, and otherwise defaults to 1.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GlobalLoanFacilityContractState>(json);
```


## Related Models

- [ContractDetails](ContractDetails.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

