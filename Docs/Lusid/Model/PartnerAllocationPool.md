# Finbourne.Sdk.Lusid.Model.PartnerAllocationPool

One pool of an allocation run: an amount of a given character, split across the partners on a basis.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Character** | **string** | Required | The character of the pool&#39;s amount, for example Income, RealisedGain or Expense. |
| **OriginMemberShortCode** | **string** | Optional | For a deal-linked pool, the short code of the member fund the amount originates from. |
| **PoolAmount** | **decimal** | Required | The amount in the pool. |
| **Basis** | **string** | Required | The basis the pool was shared on. Available values: CommittedCapital, PaidInCapital, DealPaidIn. |
| **Allocations** | [List&lt;PartnerAllocation&gt;](PartnerAllocation.md) | Required | Each partner&#39;s share of the pool. |
| **Residual** | **decimal** | Required | The rounding residual, carried by the largest allocation. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerAllocationPool(
    character: "...",  // required — The character of the pool&#39;s amount, for example Income, RealisedGain or Expense.
    originMemberShortCode: "...",  // optional — For a deal-linked pool, the short code of the member fund the amount originates from.
    poolAmount: 0.0d,  // required — The amount in the pool.
    basis: "...",  // required — The basis the pool was shared on. Available values: CommittedCapital, PaidInCapital, DealPaidIn.
    allocations: new List<PartnerAllocation>(),  // required — Each partner&#39;s share of the pool.
    residual: 0.0d  // required — The rounding residual, carried by the largest allocation.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerAllocationPool>(json);
```

- [PartnerAllocation](PartnerAllocation.md) — used in `Allocations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

