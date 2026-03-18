# Finbourne.Sdk.Lusid.Model.OrderGraphBlockOrderDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ComplianceState** | **string** | Required | The compliance state of this order. Possible values are &#39;Pending&#39;, &#39;Failed&#39;, &#39;Manually approved&#39;, &#39;Passed&#39; and &#39;Warning&#39;. |
| **ApprovalState** | **string** | Required | The approval state of this order. Possible values are &#39;Pending&#39;, &#39;Rejected&#39; and &#39;Approved&#39;. |
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
    complianceState: "...",  // required — The compliance state of this order. Possible values are &#39;Pending&#39;, &#39;Failed&#39;, &#39;Manually approved&#39;, &#39;Passed&#39; and &#39;Warning&#39;.
    approvalState: "...",  // required — The approval state of this order. Possible values are &#39;Pending&#39;, &#39;Rejected&#39; and &#39;Approved&#39;.
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

