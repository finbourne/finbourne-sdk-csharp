# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3Response

A V3 compliance rule as returned by the API: its identity and administrative fields, its full  definition, and its version.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Active** | **bool** | Optional | *No description available.* |
| **Subject** | **string** | Optional | Available values: Holdings, Orders. |
| **Filter** | [ComplianceRuleV3FilterNode](ComplianceRuleV3FilterNode.md) | Optional | *No description available.* |
| **GroupBy** | **List&lt;string&gt;** | Optional | *No description available.* |
| **Measure** | [ComplianceRuleV3Measure](ComplianceRuleV3Measure.md) | Optional | *No description available.* |
| **Check** | [ComplianceRuleV3Check](ComplianceRuleV3Check.md) | Optional | *No description available.* |
| **ComputedFilter** | [ComplianceRuleV3ComputedFilter](ComplianceRuleV3ComputedFilter.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **PlainEnglish** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3Response(
    id: new ResourceId(...),  // optional
    name: "...",  // optional
    description: "...",  // optional
    active: true,  // optional
    subject: "...",  // optional — Available values: Holdings, Orders.
    filter: new ComplianceRuleV3FilterNode(...),  // optional
    groupBy: ,  // optional
    measure: new ComplianceRuleV3Measure(...),  // optional
    check: new ComplianceRuleV3Check(...),  // optional
    computedFilter: new ComplianceRuleV3ComputedFilter(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    plainEnglish: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3Response>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceRuleV3FilterNode](ComplianceRuleV3FilterNode.md)
- [ComplianceRuleV3Measure](ComplianceRuleV3Measure.md)
- [ComplianceRuleV3Check](ComplianceRuleV3Check.md)
- [ComplianceRuleV3ComputedFilter](ComplianceRuleV3ComputedFilter.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

