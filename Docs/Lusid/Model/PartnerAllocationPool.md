# Finbourne.Sdk.Lusid.Model.PartnerAllocationPool

One pool of an allocation run: an amount of a given character, split across the partners on a basis.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Character** | **string** | Required | The character of the pool&#39;s amount, for example Income, RealisedGain or Expense. |
| **OriginMemberShortCode** | **string** | Optional | For a deal-linked pool, the short code of the member fund the amount originates from. |
| **PoolAmount** | **decimal** | Required | The amount in the pool. |
| **Basis** | **string** | Required | The basis the pool was shared on. Available values: CommittedCapital, PaidInCapital, DealPaidIn. |
| **BasisSource** | **string** | Optional | Where the figures a deal pool was shared on came from; absent on a fund-level pool, which is shared on the register&#39;s balances. Available values: DealContributions (what each partner paid into the pool&#39;s deal, from the booked allocation events), Fallback (a deal pool no partner has paid into, shared on its character&#39;s fund-level basis instead). |
| **Allocations** | [List&lt;PartnerAllocation&gt;](PartnerAllocation.md) | Required | Each partner&#39;s share of the pool. |
| **Residual** | **decimal** | Required | The rounding residual, carried by the largest allocation. |
| **PoolId** | **string** | Required | The pool&#39;s identifier: the allocation rule&#39;s bucket id, or TAG: followed by the character for lines pooled by their distribution character tag. |
| **BucketSet** | **string** | Required | The code of the allocation bucket set the pool was classified by, with its version, for example PA-ALLOCATION-v1. |
| **BasisLevel** | **string** | Required | Which level of the basis precedence decided the pool&#39;s basis. Available values: Rule (the bucket rule&#39;s own basis), CharacterDefault (the configuration&#39;s allocationBases entry for the character), BuiltIn (the built-in default for the character). |
| **Exemption** | **string** | Required | The register flag that sat partners out of the pool. Available values: None, FeeExempt, ExpenseExempt. |
| **ExcludedInvestorRecordIds** | **List&lt;string&gt;** | Optional | The partners the pool&#39;s rule left out of it. |
| **ReportRow** | **string** | Optional | The capital account row the pool&#39;s allocations land on, derived from the character. Available values: NetOperatingIncome, ManagementFeesGross, RealisedGainLoss, UnrealisedGainLoss. |
| **Sources** | [PartnerAllocationPoolSources](PartnerAllocationPoolSources.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerAllocationPool(
    character: "...",  // required — The character of the pool&#39;s amount, for example Income, RealisedGain or Expense.
    originMemberShortCode: "...",  // optional — For a deal-linked pool, the short code of the member fund the amount originates from.
    poolAmount: 0.0d,  // required — The amount in the pool.
    basis: "...",  // required — The basis the pool was shared on. Available values: CommittedCapital, PaidInCapital, DealPaidIn.
    basisSource: "...",  // optional — Where the figures a deal pool was shared on came from; absent on a fund-level pool, which is shared on the register&#39;s balances. Available values: DealContributions (what each partner paid into the pool&#39;s deal, from the booked allocation events), Fallback (a deal pool no partner has paid into, shared on its character&#39;s fund-level basis instead).
    allocations: new List<PartnerAllocation>(),  // required — Each partner&#39;s share of the pool.
    residual: 0.0d,  // required — The rounding residual, carried by the largest allocation.
    poolId: "...",  // required — The pool&#39;s identifier: the allocation rule&#39;s bucket id, or TAG: followed by the character for lines pooled by their distribution character tag.
    bucketSet: "...",  // required — The code of the allocation bucket set the pool was classified by, with its version, for example PA-ALLOCATION-v1.
    basisLevel: "...",  // required — Which level of the basis precedence decided the pool&#39;s basis. Available values: Rule (the bucket rule&#39;s own basis), CharacterDefault (the configuration&#39;s allocationBases entry for the character), BuiltIn (the built-in default for the character).
    exemption: "...",  // required — The register flag that sat partners out of the pool. Available values: None, FeeExempt, ExpenseExempt.
    excludedInvestorRecordIds: ,  // optional — The partners the pool&#39;s rule left out of it.
    reportRow: "...",  // optional — The capital account row the pool&#39;s allocations land on, derived from the character. Available values: NetOperatingIncome, ManagementFeesGross, RealisedGainLoss, UnrealisedGainLoss.
    sources: new PartnerAllocationPoolSources(...)  // required
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
- [PartnerAllocationPoolSources](PartnerAllocationPoolSources.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

