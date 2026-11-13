# Finbourne.Sdk.Lusid.Model.ComplianceSummaryRuleResultWithContributions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **CheckType** | **string** | Optional | The kind of check the rule applied across its groups: \&quot;PercentCheck\&quot; or \&quot;Check\&quot;. Static per rule. Absent for a  rule no check reached. |
| **AffectedPortfolios** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **AffectedOrders** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The orders the rule affected. Omitted for a holdings-based run. |
| **Groups** | [List&lt;ComplianceRuleBreakdownWithContributions&gt;](ComplianceRuleBreakdownWithContributions.md) | Required | *No description available.* |
| **OtherPositionsConsidered** | [List&lt;ComplianceRuleContribution&gt;](ComplianceRuleContribution.md) | Optional | The rest of the basis the rule was measured against but did not directly evaluate — the positions in  the referenced/denominator (or initial) group that are not in a group&#39;s contributions. Together with those  contributions this forms the whole basis, with no overlap, so a breach can be explained against the full picture  (e.g. the non-equity remainder behind an equity limit). Omitted when the rule evaluated everything it considered. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceSummaryRuleResultWithContributions(
    ruleId: new ResourceId(...),  // required
    status: "...",  // required
    checkType: "...",  // optional — The kind of check the rule applied across its groups: \&quot;PercentCheck\&quot; or \&quot;Check\&quot;. Static per rule. Absent for a  rule no check reached.
    affectedPortfolios: new List<ResourceId>(),  // required
    affectedOrders: new List<ResourceId>(),  // optional — The orders the rule affected. Omitted for a holdings-based run.
    groups: new List<ComplianceRuleBreakdownWithContributions>(),  // required
    otherPositionsConsidered: new List<ComplianceRuleContribution>()  // optional — The rest of the basis the rule was measured against but did not directly evaluate — the positions in  the referenced/denominator (or initial) group that are not in a group&#39;s contributions. Together with those  contributions this forms the whole basis, with no overlap, so a breach can be explained against the full picture  (e.g. the non-equity remainder behind an equity limit). Omitted when the rule evaluated everything it considered.
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
- [ResourceId](ResourceId.md) — used in `AffectedOrders`
- [ComplianceRuleBreakdownWithContributions](ComplianceRuleBreakdownWithContributions.md)
- [ComplianceRuleContribution](ComplianceRuleContribution.md) — used in `OtherPositionsConsidered`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

