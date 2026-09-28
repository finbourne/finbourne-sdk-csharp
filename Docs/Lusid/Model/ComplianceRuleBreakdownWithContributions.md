# Finbourne.Sdk.Lusid.Model.ComplianceRuleBreakdownWithContributions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupStatus** | **string** | Required | The status of this subset of results. |
| **ResultsUsed** | **Dictionary&lt;string, decimal&gt;** | Required | Dictionary of AddressKey (as string) and their corresponding decimal values, that were used in this rule. |
| **PropertiesUsed** | **Dictionary&lt;string, List&lt;Property&gt;&gt;** | Required | Dictionary of PropertyKey (as string) and their corresponding Properties, that were used in this rule |
| **MissingDataInformation** | **List&lt;string&gt;** | Required | List of string information detailing data that was missing from contributions processed in this rule |
| **Lineage** | [List&lt;LineageMember&gt;](LineageMember.md) | Required | *No description available.* |
| **Contributions** | [List&lt;ComplianceRuleContribution&gt;](ComplianceRuleContribution.md) | Required | The per-position contributions aggregated into this rule breakdown group. Empty when the run  genuinely produced no contributions; a run with no recorded breakdown (e.g. one that predates  this feature) returns a 404 rather than this response. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleBreakdownWithContributions(
    groupStatus: "...",  // required — The status of this subset of results.
    resultsUsed: ,  // required — Dictionary of AddressKey (as string) and their corresponding decimal values, that were used in this rule.
    propertiesUsed: ,  // required — Dictionary of PropertyKey (as string) and their corresponding Properties, that were used in this rule
    missingDataInformation: ,  // required — List of string information detailing data that was missing from contributions processed in this rule
    lineage: new List<LineageMember>(),  // required
    contributions: new List<ComplianceRuleContribution>()  // required — The per-position contributions aggregated into this rule breakdown group. Empty when the run  genuinely produced no contributions; a run with no recorded breakdown (e.g. one that predates  this feature) returns a 404 rather than this response.
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

- [LineageMember](LineageMember.md)
- [ComplianceRuleContribution](ComplianceRuleContribution.md) — used in `Contributions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

