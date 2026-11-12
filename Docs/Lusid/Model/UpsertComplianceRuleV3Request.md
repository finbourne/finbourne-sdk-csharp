# Finbourne.Sdk.Lusid.Model.UpsertComplianceRuleV3Request

A request to create or update a V3 compliance rule. A V3 rule's own record fully describes what it  checks: the subject it runs over, the filter selecting rows, the grouping and measure reducing them to a  number, and the check that number must satisfy. Shares no type with ComplianceV1/V2.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Active** | **bool** | Required | *No description available.* |
| **Subject** | **string** | Required | Available values: Holdings, Orders. |
| **Filter** | [ComplianceRuleV3FilterNode](ComplianceRuleV3FilterNode.md) | Optional | *No description available.* |
| **GroupBy** | **List&lt;string&gt;** | Optional | *No description available.* |
| **Measure** | [ComplianceRuleV3Measure](ComplianceRuleV3Measure.md) | Required | *No description available.* |
| **Check** | [ComplianceRuleV3Check](ComplianceRuleV3Check.md) | Required | *No description available.* |
| **ComputedFilter** | [ComplianceRuleV3ComputedFilter](ComplianceRuleV3ComputedFilter.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertComplianceRuleV3Request(
    id: new ResourceId(...),  // required
    name: "...",  // optional
    description: "...",  // optional
    active: true,  // required
    subject: "...",  // required — Available values: Holdings, Orders.
    filter: new ComplianceRuleV3FilterNode(...),  // optional
    groupBy: ,  // optional
    measure: new ComplianceRuleV3Measure(...),  // required
    check: new ComplianceRuleV3Check(...),  // required
    computedFilter: new ComplianceRuleV3ComputedFilter(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertComplianceRuleV3Request>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceRuleV3FilterNode](ComplianceRuleV3FilterNode.md)
- [ComplianceRuleV3Measure](ComplianceRuleV3Measure.md)
- [ComplianceRuleV3Check](ComplianceRuleV3Check.md)
- [ComplianceRuleV3ComputedFilter](ComplianceRuleV3ComputedFilter.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

