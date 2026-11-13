# Finbourne.Sdk.Lusid.Model.ComplianceRuleBreakdownWithContributions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupId** | **int** | Required | A stable identifier for this group within the rule, matching the same group in the rule-result endpoint. |
| **Status** | **string** | Required | The status of this subset of results. |
| **GroupKey** | [ComplianceGroupKey](ComplianceGroupKey.md) | Optional | *No description available.* |
| **Nav** | **decimal?** | Optional | The portfolio net asset value the group sits within. Absent where no contribution carried it. |
| **Results** | **Dictionary&lt;string, decimal&gt;** | Optional | The valuation result totals the group aggregated. Omitted when empty. |
| **Comparisons** | [List&lt;ComplianceComparison&gt;](ComplianceComparison.md) | Optional | Every leaf comparison the check criterion made for this group, drawn from both the hard and the soft limit.  Omitted for a group no check reached. |
| **Properties** | **Dictionary&lt;string, List&lt;Property&gt;&gt;** | Optional | The property values the group aggregated. Omitted when empty. |
| **FormulaValues** | **Dictionary&lt;string, decimal&gt;** | Optional | The value each formula within the check criterion evaluated to for this group. Omitted when empty. |
| **Contributions** | [List&lt;ComplianceRuleContribution&gt;](ComplianceRuleContribution.md) | Required | The per-position contributions aggregated into this rule breakdown group. Empty when the run  genuinely produced no contributions; a run with no recorded breakdown (e.g. one that predates  this feature) returns a 404 rather than this response. |
| **MissingDataInformation** | **List&lt;string&gt;** | Optional | List of string information detailing data that was missing from contributions processed in this rule. Omitted when empty. |
| **ContributionCount** | **int** | Required | The number of contributions aggregated into this group, before any cap. |
| **ContributionsTruncated** | **bool** | Required | Whether the reported contributions were capped below ContributionCount. Always false today. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleBreakdownWithContributions(
    groupId: 0,  // required — A stable identifier for this group within the rule, matching the same group in the rule-result endpoint.
    status: "...",  // required — The status of this subset of results.
    groupKey: new ComplianceGroupKey(...),  // optional
    nav: 0.0d,  // optional — The portfolio net asset value the group sits within. Absent where no contribution carried it.
    results: ,  // optional — The valuation result totals the group aggregated. Omitted when empty.
    comparisons: new List<ComplianceComparison>(),  // optional — Every leaf comparison the check criterion made for this group, drawn from both the hard and the soft limit.  Omitted for a group no check reached.
    properties: ,  // optional — The property values the group aggregated. Omitted when empty.
    formulaValues: ,  // optional — The value each formula within the check criterion evaluated to for this group. Omitted when empty.
    contributions: new List<ComplianceRuleContribution>(),  // required — The per-position contributions aggregated into this rule breakdown group. Empty when the run  genuinely produced no contributions; a run with no recorded breakdown (e.g. one that predates  this feature) returns a 404 rather than this response.
    missingDataInformation: ,  // optional — List of string information detailing data that was missing from contributions processed in this rule. Omitted when empty.
    contributionCount: 0,  // required — The number of contributions aggregated into this group, before any cap.
    contributionsTruncated: true  // required — Whether the reported contributions were capped below ContributionCount. Always false today.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleBreakdownWithContributions>(json);
```

- [ComplianceGroupKey](ComplianceGroupKey.md)
- [ComplianceComparison](ComplianceComparison.md) — used in `Comparisons`
- [ComplianceRuleContribution](ComplianceRuleContribution.md) — used in `Contributions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

