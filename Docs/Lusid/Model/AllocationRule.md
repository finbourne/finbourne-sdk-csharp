# Finbourne.Sdk.Lusid.Model.AllocationRule

The allocation character of one P&L or fees bucket of the allocation bucket set, and optionally how its pools  are shared, echoed as stored. The effective block, overridden fields and source are derived on the way out and  ignored on the way in, so a read written back pins nothing.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BucketId** | **string** | Required | The bucket of the allocation bucket set the rule applies to. |
| **Character** | **string** | Optional | The allocation character of the bucket&#39;s lines, which decides the capital account row. Available values: Income, RealisedGain, UnrealisedGain, OtherIncome, ManagementFee, Expense. Fixed by the set, and so omitted, when the allocation bucket set is a system set. |
| **Basis** | **string** | Optional | The register balance the bucket&#39;s pools are shared on. Available values: CommittedCapital, PaidInCapital. Omit to take the character&#39;s default from allocationBases or the built-in default; returned as stored, with what the fund uses under effective. A pool that names its origin member is shared on deal paid-in unless its rule names a basis, and a rule may not ask for deal paid-in. Available values: CommittedCapital, PaidInCapital. |
| **Exemption** | **string** | Optional | Which register flag sits a partner out of the bucket&#39;s pools. Available values: None, FeeExempt, ExpenseExempt. Omit to take the character&#39;s default (FeeExempt for ManagementFee, ExpenseExempt for Expense, otherwise None); returned as stored, with what the fund uses under effective. Available values: None, FeeExempt, ExpenseExempt. |
| **ExcludedInvestorRecordIds** | **List&lt;string&gt;** | Optional | Investor records that sit out every pool of the bucket. Optional. |
| **Effective** | [AllocationRuleEffective](AllocationRuleEffective.md) | Optional | *No description available.* |
| **OverriddenFields** | **List&lt;string&gt;** | Optional | On a system set&#39;s rule, the fields this configuration overrides; absent on a configuration&#39;s own rule. Read-only. |
| **Source** | **string** | Optional | Where the rule&#39;s character comes from: System for a released system set, Configuration for the configuration&#39;s own set. Read-only. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationRule(
    bucketId: "...",  // required — The bucket of the allocation bucket set the rule applies to.
    character: "...",  // optional — The allocation character of the bucket&#39;s lines, which decides the capital account row. Available values: Income, RealisedGain, UnrealisedGain, OtherIncome, ManagementFee, Expense. Fixed by the set, and so omitted, when the allocation bucket set is a system set.
    basis: "...",  // optional — The register balance the bucket&#39;s pools are shared on. Available values: CommittedCapital, PaidInCapital. Omit to take the character&#39;s default from allocationBases or the built-in default; returned as stored, with what the fund uses under effective. A pool that names its origin member is shared on deal paid-in unless its rule names a basis, and a rule may not ask for deal paid-in. Available values: CommittedCapital, PaidInCapital.
    exemption: "...",  // optional — Which register flag sits a partner out of the bucket&#39;s pools. Available values: None, FeeExempt, ExpenseExempt. Omit to take the character&#39;s default (FeeExempt for ManagementFee, ExpenseExempt for Expense, otherwise None); returned as stored, with what the fund uses under effective. Available values: None, FeeExempt, ExpenseExempt.
    excludedInvestorRecordIds: ,  // optional — Investor records that sit out every pool of the bucket. Optional.
    effective: new AllocationRuleEffective(...),  // optional
    overriddenFields: ,  // optional — On a system set&#39;s rule, the fields this configuration overrides; absent on a configuration&#39;s own rule. Read-only.
    source: "..."  // optional — Where the rule&#39;s character comes from: System for a released system set, Configuration for the configuration&#39;s own set. Read-only.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationRule>(json);
```

- [AllocationRuleEffective](AllocationRuleEffective.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

