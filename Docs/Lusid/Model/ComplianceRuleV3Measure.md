# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3Measure

How a rule reduces its filtered (and optionally grouped) subject rows to the single number a check is  applied to: a metric field, the aggregate combining its values, and what it is expressed relative to.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Metric** | **string** | Optional | *No description available.* |
| **Aggregate** | **string** | Required | Available values: Sum, Min, Max, Average, Count, CountDistinct, WeightedSum, SumAbsolute. |
| **Denominator** | **string** | Optional | Available values: None, PortfolioValue, GrossValue, NetValue, FilteredSubsetTotal, GroupNav, GroupGrossExposure, GroupFilteredSubsetTotal. |
| **DenominatorMetric** | **string** | Optional | *No description available.* |
| **WeightMetric** | **string** | Optional | *No description available.* |
| **DenominatorProperty** | **string** | Optional | *No description available.* |
| **Filter** | [ComplianceRuleV3FilterNode](ComplianceRuleV3FilterNode.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3Measure(
    metric: "...",  // optional
    aggregate: "...",  // required — Available values: Sum, Min, Max, Average, Count, CountDistinct, WeightedSum, SumAbsolute.
    denominator: "...",  // optional — Available values: None, PortfolioValue, GrossValue, NetValue, FilteredSubsetTotal, GroupNav, GroupGrossExposure, GroupFilteredSubsetTotal.
    denominatorMetric: "...",  // optional
    weightMetric: "...",  // optional
    denominatorProperty: "...",  // optional
    filter: new ComplianceRuleV3FilterNode(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3Measure>(json);
```

- [ComplianceRuleV3FilterNode](ComplianceRuleV3FilterNode.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

