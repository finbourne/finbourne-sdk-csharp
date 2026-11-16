# Finbourne.Sdk.Lusid.Model.AllocationRuleEffective

What a rule's pools actually use once the defaults are applied. Read-only: derived on the way out and ignored on  the way in.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Basis** | **string** | Required | The basis the bucket&#39;s fund-level pools are shared on. Available values: CommittedCapital, PaidInCapital. |
| **Exemption** | **string** | Required | The register flag that sits partners out of the bucket&#39;s pools. Available values: None, FeeExempt, ExpenseExempt. |
| **ReportRow** | **string** | Optional | The capital account row the bucket&#39;s allocations land on, derived from the character. Available values: NetOperatingIncome, ManagementFeesGross, RealisedGainLoss, UnrealisedGainLoss. |
| **BasisLevel** | **string** | Required | Which level of the basis precedence decided the basis. Available values: Rule, CharacterDefault, BuiltIn. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationRuleEffective(
    basis: "...",  // required — The basis the bucket&#39;s fund-level pools are shared on. Available values: CommittedCapital, PaidInCapital.
    exemption: "...",  // required — The register flag that sits partners out of the bucket&#39;s pools. Available values: None, FeeExempt, ExpenseExempt.
    reportRow: "...",  // optional — The capital account row the bucket&#39;s allocations land on, derived from the character. Available values: NetOperatingIncome, ManagementFeesGross, RealisedGainLoss, UnrealisedGainLoss.
    basisLevel: "..."  // required — Which level of the basis precedence decided the basis. Available values: Rule, CharacterDefault, BuiltIn.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationRuleEffective>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

