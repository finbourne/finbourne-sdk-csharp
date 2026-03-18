# Finbourne.Sdk.Lusid.Model.ComplianceRuleResultDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AffectedPortfoliosDetails** | [List&lt;ComplianceRuleResultPortfolioDetail&gt;](ComplianceRuleResultPortfolioDetail.md) | Required | *No description available.* |
| **AffectedOrders** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **TemplateId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TemplateDescription** | **string** | Required | *No description available.* |
| **TemplateVariation** | **string** | Required | *No description available.* |
| **Status** | **string** | Required | *No description available.* |
| **RuleName** | **string** | Required | *No description available.* |
| **RuleDescription** | **string** | Required | *No description available.* |
| **Outcome** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleResultDetail(
    ruleId: new ResourceId(...),  // required
    affectedPortfoliosDetails: new List<ComplianceRuleResultPortfolioDetail>(),  // required
    affectedOrders: new List<ResourceId>(),  // required
    templateId: new ResourceId(...),  // required
    templateDescription: "...",  // required
    templateVariation: "...",  // required
    status: "...",  // required
    ruleName: "...",  // required
    ruleDescription: "...",  // required
    outcome: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleResultDetail>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceRuleResultPortfolioDetail](ComplianceRuleResultPortfolioDetail.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

