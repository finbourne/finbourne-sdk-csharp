# Finbourne.Sdk.Lusid.Model.WithholdingTaxResolution

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ResolutionStatus** | **string** | Required | Match or NoMatch: the status booking stamps on a transaction. |
| **MatchedRule** | [WithholdingTaxMatchedRule](WithholdingTaxMatchedRule.md) | Optional | *No description available.* |
| **RateTiers** | [WithholdingTaxRateTiers](WithholdingTaxRateTiers.md) | Optional | *No description available.* |
| **RasFlags** | [WithholdingTaxReliefAtSourceFlags](WithholdingTaxReliefAtSourceFlags.md) | Optional | *No description available.* |
| **DerivedSplit** | [WithholdingTaxRateSplit](WithholdingTaxRateSplit.md) | Optional | *No description available.* |
| **Provenance** | [WithholdingTaxResolutionProvenance](WithholdingTaxResolutionProvenance.md) | Optional | *No description available.* |
| **ResolvedDimensions** | **Dictionary&lt;string, string&gt;** | Required | Each dimension of either dataset, with the value used. Null where there is no value. |
| **IsWhatIf** | **bool** | Required | False when the saved configuration&#39;s datasets and source order are used as they are. True when a dataset or the source order differs from the configuration&#39;s, or when no configuration was given. |
| **UnresolvedDimensions** | [Dictionary&lt;string, WithholdingTaxUnresolvedDimension&gt;](WithholdingTaxUnresolvedDimension.md) | Required | Each dimension that booking reads from the transaction, portfolio or fund, that dimensions does not supply, and that a couldAlsoMatch entry needs. It is null, so only rows blank on it match. Empty in Raw mode. |
| **CouldAlsoMatch** | [List&lt;WithholdingTaxAlternativeMatch&gt;](WithholdingTaxAlternativeMatch.md) | Required | Each other row that booking would choose with its own values for the unresolved dimensions, fewest values first, up to the limit. Where one entry&#39;s values include another&#39;s, the one with more values applies. |
| **HasMoreAlternatives** | **bool** | Required | True when the limit stopped the lookup before it tried every combination of values, so couldAlsoMatch may miss rows. Ask again with a higher limit. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxResolution(
    resolutionStatus: "...",  // required — Match or NoMatch: the status booking stamps on a transaction.
    matchedRule: new WithholdingTaxMatchedRule(...),  // optional
    rateTiers: new WithholdingTaxRateTiers(...),  // optional
    rasFlags: new WithholdingTaxReliefAtSourceFlags(...),  // optional
    derivedSplit: new WithholdingTaxRateSplit(...),  // optional
    provenance: new WithholdingTaxResolutionProvenance(...),  // optional
    resolvedDimensions: ,  // required — Each dimension of either dataset, with the value used. Null where there is no value.
    isWhatIf: true,  // required — False when the saved configuration&#39;s datasets and source order are used as they are. True when a dataset or the source order differs from the configuration&#39;s, or when no configuration was given.
    unresolvedDimensions: new WithholdingTaxUnresolvedDimension(...),  // required — Each dimension that booking reads from the transaction, portfolio or fund, that dimensions does not supply, and that a couldAlsoMatch entry needs. It is null, so only rows blank on it match. Empty in Raw mode.
    couldAlsoMatch: new List<WithholdingTaxAlternativeMatch>(),  // required — Each other row that booking would choose with its own values for the unresolved dimensions, fewest values first, up to the limit. Where one entry&#39;s values include another&#39;s, the one with more values applies.
    hasMoreAlternatives: true  // required — True when the limit stopped the lookup before it tried every combination of values, so couldAlsoMatch may miss rows. Ask again with a higher limit.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxResolution>(json);
```

- [WithholdingTaxMatchedRule](WithholdingTaxMatchedRule.md)
- [WithholdingTaxRateTiers](WithholdingTaxRateTiers.md)
- [WithholdingTaxReliefAtSourceFlags](WithholdingTaxReliefAtSourceFlags.md)
- [WithholdingTaxRateSplit](WithholdingTaxRateSplit.md)
- [WithholdingTaxResolutionProvenance](WithholdingTaxResolutionProvenance.md)
- [WithholdingTaxUnresolvedDimension](WithholdingTaxUnresolvedDimension.md) — used in `UnresolvedDimensions`
- [WithholdingTaxAlternativeMatch](WithholdingTaxAlternativeMatch.md) — used in `CouldAlsoMatch`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

