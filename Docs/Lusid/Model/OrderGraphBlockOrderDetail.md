# Finbourne.Sdk.Lusid.Model.OrderGraphBlockOrderDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ComplianceState** | **string** | Required | The compliance state of this order. Available values: Pending, Failed, Passed, ManuallyApproved, PartiallyOverridden, Warning. |
| **ApprovalState** | **string** | Required | The approval state of this order. Available values: Pending, Rejected, Approved. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioName** | **string** | Optional | The name of the order&#39;s referenced Portfolio. |
| **OrderApprovalTaskId** | **string** | Optional | The task id associated with the approval state of the order. |
| **OrderApprovalTaskDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **NonPassingComplianceRuleResults** | [List&lt;ContributionToNonPassingRuleDetail&gt;](ContributionToNonPassingRuleDetail.md) | Optional | The details of compliance rules in non-passing states. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockOrderDetail(
    id: new ResourceId(...),  // required
    complianceState: "...",  // required — The compliance state of this order. Available values: Pending, Failed, Passed, ManuallyApproved, PartiallyOverridden, Warning.
    approvalState: "...",  // required — The approval state of this order. Available values: Pending, Rejected, Approved.
    portfolioId: new ResourceId(...),  // optional
    portfolioName: "...",  // optional — The name of the order&#39;s referenced Portfolio.
    orderApprovalTaskId: "...",  // optional — The task id associated with the approval state of the order.
    orderApprovalTaskDefinitionId: new ResourceId(...),  // optional
    nonPassingComplianceRuleResults: new List<ContributionToNonPassingRuleDetail>()  // optional — The details of compliance rules in non-passing states.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockOrderDetail>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ContributionToNonPassingRuleDetail](ContributionToNonPassingRuleDetail.md) — used in `NonPassingComplianceRuleResults`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

