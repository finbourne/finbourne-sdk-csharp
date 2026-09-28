# Finbourne.Sdk.Lusid.Model.ComplianceSummaryRuleResultWithContributions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TemplateId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Variation** | **string** | Required | *No description available.* |
| **RuleStatus** | **string** | Required | *No description available.* |
| **AffectedPortfolios** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **AffectedOrders** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **ParametersUsed** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **RuleBreakdown** | [List&lt;ComplianceRuleBreakdownWithContributions&gt;](ComplianceRuleBreakdownWithContributions.md) | Required | *No description available.* |
| **OtherPositionsConsidered** | [List&lt;ComplianceRuleContribution&gt;](ComplianceRuleContribution.md) | Required | The rest of the basis the rule was measured against but did not directly evaluate — the positions in  the referenced/denominator (or initial) group that are not in the RuleBreakdown&#39;s  contributions. Together with those contributions this forms the whole basis, with no overlap, so a  breach can be explained against the full picture (e.g. the non-equity remainder behind an equity limit).  Empty when the rule evaluated everything it considered. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceSummaryRuleResultWithContributions(
    ruleId: new ResourceId(...),  // required
    templateId: new ResourceId(...),  // required
    variation: "...",  // required
    ruleStatus: "...",  // required
    affectedPortfolios: new List<ResourceId>(),  // required
    affectedOrders: new List<ResourceId>(),  // required
    parametersUsed: ,  // required
    ruleBreakdown: new List<ComplianceRuleBreakdownWithContributions>(),  // required
    otherPositionsConsidered: new List<ComplianceRuleContribution>()  // required — The rest of the basis the rule was measured against but did not directly evaluate — the positions in  the referenced/denominator (or initial) group that are not in the RuleBreakdown&#39;s  contributions. Together with those contributions this forms the whole basis, with no overlap, so a  breach can be explained against the full picture (e.g. the non-equity remainder behind an equity limit).  Empty when the rule evaluated everything it considered.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceSummaryRuleResultWithContributions>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ComplianceRuleBreakdownWithContributions](ComplianceRuleBreakdownWithContributions.md)
- [ComplianceRuleContribution](ComplianceRuleContribution.md) — used in `OtherPositionsConsidered`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

