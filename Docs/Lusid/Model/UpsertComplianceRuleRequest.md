# Finbourne.Sdk.Lusid.Model.UpsertComplianceRuleRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Active** | **bool** | Required | *No description available.* |
| **TemplateId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Variation** | **string** | Required | *No description available.* |
| **PortfolioGroupId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Parameters** | [Dictionary&lt;string, ComplianceParameter&gt;](ComplianceParameter.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertComplianceRuleRequest(
    id: new ResourceId(...),  // required
    name: "...",  // optional
    description: "...",  // optional
    active: true,  // required
    templateId: new ResourceId(...),  // required
    variation: "...",  // required
    portfolioGroupId: new ResourceId(...),  // required
    parameters: new ComplianceParameter(...),  // required
    properties: new PerpetualProperty(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertComplianceRuleRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ComplianceParameter](ComplianceParameter.md)
- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

