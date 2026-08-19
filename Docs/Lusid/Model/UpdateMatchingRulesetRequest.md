# Finbourne.Sdk.Lusid.Model.UpdateMatchingRulesetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the matching ruleset. |
| **RecType** | **string** | Required | The type of reconciliation to perform. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity. |
| **DatasetSchemas** | [RecDatasetSchemas](RecDatasetSchemas.md) | Optional | *No description available.* |
| **Filters** | [GroupReconciliationFilters](GroupReconciliationFilters.md) | Optional | *No description available.* |
| **CoreRules** | [List&lt;CoreMatchingRule&gt;](CoreMatchingRule.md) | Required | The core comparison rules evaluated as derivation formulae against each side of the reconciliation. |
| **AggregateRules** | [List&lt;AggregateMatchingRule&gt;](AggregateMatchingRule.md) | Required | The aggregate comparison rules evaluated as derivation formulae against values on each side of the reconciliation and operation to aggregate those values. |
| **CoreTolerances** | [List&lt;ToleranceBase&gt;](ToleranceBase.md) | Optional | Tolerance configurations applied to core rule matching, in the specified order. |
| **AggregateTolerances** | [List&lt;ToleranceBase&gt;](ToleranceBase.md) | Optional | Tolerance configurations applied to aggregate rule matching. |
| **AllowPartialMatching** | **bool** | Optional | Whether to permit partial matches when applying rules. |
| **SupplementalAttributes** | [List&lt;SupplementalAttribute&gt;](SupplementalAttribute.md) | Optional | Supplemental attributes that decorate reconciliation results with additional values without participating in the reconciliation itself. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateMatchingRulesetRequest(
    displayName: "...",  // required — The name of the matching ruleset.
    recType: "...",  // required — The type of reconciliation to perform. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity.
    datasetSchemas: new RecDatasetSchemas(...),  // optional
    filters: new GroupReconciliationFilters(...),  // optional
    coreRules: new List<CoreMatchingRule>(),  // required — The core comparison rules evaluated as derivation formulae against each side of the reconciliation.
    aggregateRules: new List<AggregateMatchingRule>(),  // required — The aggregate comparison rules evaluated as derivation formulae against values on each side of the reconciliation and operation to aggregate those values.
    coreTolerances: new List<ToleranceBase>(),  // optional — Tolerance configurations applied to core rule matching, in the specified order.
    aggregateTolerances: new List<ToleranceBase>(),  // optional — Tolerance configurations applied to aggregate rule matching.
    allowPartialMatching: true,  // optional — Whether to permit partial matches when applying rules.
    supplementalAttributes: new List<SupplementalAttribute>()  // optional — Supplemental attributes that decorate reconciliation results with additional values without participating in the reconciliation itself.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateMatchingRulesetRequest>(json);
```

- [RecDatasetSchemas](RecDatasetSchemas.md)
- [GroupReconciliationFilters](GroupReconciliationFilters.md)
- [CoreMatchingRule](CoreMatchingRule.md) — used in `CoreRules`
- [AggregateMatchingRule](AggregateMatchingRule.md) — used in `AggregateRules`
- [ToleranceBase](ToleranceBase.md) — used in `CoreTolerances`
- [ToleranceBase](ToleranceBase.md) — used in `AggregateTolerances`
- [SupplementalAttribute](SupplementalAttribute.md) — used in `SupplementalAttributes`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

