# Finbourne.Sdk.Lusid.Model.ComplianceSummaryRuleResultRequest

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
| **RuleBreakdown** | [List&lt;ComplianceRuleBreakdownRequest&gt;](ComplianceRuleBreakdownRequest.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceSummaryRuleResultRequest(
    ruleId: new ResourceId(...),  // required
    templateId: new ResourceId(...),  // required
    variation: "...",  // required
    ruleStatus: "...",  // required
    affectedPortfolios: new List<ResourceId>(),  // required
    affectedOrders: new List<ResourceId>(),  // required
    parametersUsed: ,  // required
    ruleBreakdown: new List<ComplianceRuleBreakdownRequest>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceSummaryRuleResultRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ComplianceRuleBreakdownRequest](ComplianceRuleBreakdownRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

