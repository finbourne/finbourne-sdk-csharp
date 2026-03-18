# Finbourne.Sdk.Lusid.Model.GroupReconciliationComparisonResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ReconciliationType** | **string** | Required | The type of reconciliation to perform. \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot; |
| **GroupReconciliationDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstanceId** | [GroupReconciliationInstanceId](GroupReconciliationInstanceId.md) | Required | *No description available.* |
| **ComparisonResultId** | **string** | Required | Comparison result identifier, encoded value for core attribute results, aggregate attribute results, reconciliation type and run instanceId. |
| **ReconciliationRunAsAt** | **DateTimeOffset** | Required | The timestamp when the run occurred. |
| **ResultType** | **string** | Required | Reconciliation run general result. \&quot;Break\&quot; | \&quot;Match\&quot; | \&quot;PartialMatch\&quot; | \&quot;NotFound |
| **ResultStatus** | **string** | Required | Indicates how a particular result evolves from one run to the next. \&quot;New\&quot; | \&quot;Confirmed\&quot; | \&quot;Changed\&quot; |
| **ReviewStatus** | **string** | Required | Status of whether user has provided any input (comments, manual matches, break codes). \&quot;Pending\&quot; | \&quot;Reviewed\&quot; | \&quot;Matched\&quot; | \&quot;Invalid\&quot; |
| **DatesReconciled** | [GroupReconciliationDates](GroupReconciliationDates.md) | Required | *No description available.* |
| **CoreAttributes** | [GroupReconciliationCoreAttributeValues](GroupReconciliationCoreAttributeValues.md) | Required | *No description available.* |
| **AggregateAttributes** | [GroupReconciliationAggregateAttributeValues](GroupReconciliationAggregateAttributeValues.md) | Required | *No description available.* |
| **UserReview** | [GroupReconciliationUserReview](GroupReconciliationUserReview.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationComparisonResult(
    id: new ResourceId(...),  // required
    reconciliationType: "...",  // required — The type of reconciliation to perform. \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot;
    groupReconciliationDefinitionId: new ResourceId(...),  // required
    instanceId: new GroupReconciliationInstanceId(...),  // required
    comparisonResultId: "...",  // required — Comparison result identifier, encoded value for core attribute results, aggregate attribute results, reconciliation type and run instanceId.
    reconciliationRunAsAt: DateTimeOffset.Now,  // required — The timestamp when the run occurred.
    resultType: "...",  // required — Reconciliation run general result. \&quot;Break\&quot; | \&quot;Match\&quot; | \&quot;PartialMatch\&quot; | \&quot;NotFound
    resultStatus: "...",  // required — Indicates how a particular result evolves from one run to the next. \&quot;New\&quot; | \&quot;Confirmed\&quot; | \&quot;Changed\&quot;
    reviewStatus: "...",  // required — Status of whether user has provided any input (comments, manual matches, break codes). \&quot;Pending\&quot; | \&quot;Reviewed\&quot; | \&quot;Matched\&quot; | \&quot;Invalid\&quot;
    datesReconciled: new GroupReconciliationDates(...),  // required
    coreAttributes: new GroupReconciliationCoreAttributeValues(...),  // required
    aggregateAttributes: new GroupReconciliationAggregateAttributeValues(...),  // required
    userReview: new GroupReconciliationUserReview(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationComparisonResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [GroupReconciliationInstanceId](GroupReconciliationInstanceId.md)
- [GroupReconciliationDates](GroupReconciliationDates.md)
- [GroupReconciliationCoreAttributeValues](GroupReconciliationCoreAttributeValues.md)
- [GroupReconciliationAggregateAttributeValues](GroupReconciliationAggregateAttributeValues.md)
- [GroupReconciliationUserReview](GroupReconciliationUserReview.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

