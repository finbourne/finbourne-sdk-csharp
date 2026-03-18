# Finbourne.Sdk.Lusid.Model.GroupReconciliationSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunDetails** | [GroupReconciliationRunDetails](GroupReconciliationRunDetails.md) | Optional | *No description available.* |
| **GroupReconciliationDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **ReconciliationType** | **string** | Required | The type of reconciliation to perform. \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot; |
| **InstanceId** | [GroupReconciliationInstanceId](GroupReconciliationInstanceId.md) | Required | *No description available.* |
| **DatesReconciled** | [GroupReconciliationDates](GroupReconciliationDates.md) | Required | *No description available.* |
| **ReconciliationRunAsAt** | **DateTimeOffset** | Required | The date and time the reconciliation was run |
| **CountComparisonResults** | **int** | Required | The total number of comparison results with this InstanceId and ReconciliationType |
| **LinkComparisonResults** | [Link](Link.md) | Optional | *No description available.* |
| **ResultTypes** | [GroupReconciliationResultTypes](GroupReconciliationResultTypes.md) | Optional | *No description available.* |
| **ResultStatuses** | [GroupReconciliationResultStatuses](GroupReconciliationResultStatuses.md) | Optional | *No description available.* |
| **ReviewStatuses** | [GroupReconciliationReviewStatuses](GroupReconciliationReviewStatuses.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationSummary(
    runDetails: new GroupReconciliationRunDetails(...),  // optional
    groupReconciliationDefinitionId: new ResourceId(...),  // optional
    reconciliationType: "...",  // required — The type of reconciliation to perform. \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot;
    instanceId: new GroupReconciliationInstanceId(...),  // required
    datesReconciled: new GroupReconciliationDates(...),  // required
    reconciliationRunAsAt: DateTimeOffset.Now,  // required — The date and time the reconciliation was run
    countComparisonResults: 0,  // required — The total number of comparison results with this InstanceId and ReconciliationType
    linkComparisonResults: new Link(...),  // optional
    resultTypes: new GroupReconciliationResultTypes(...),  // optional
    resultStatuses: new GroupReconciliationResultStatuses(...),  // optional
    reviewStatuses: new GroupReconciliationReviewStatuses(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationSummary>(json);
```


## Related Models

- [GroupReconciliationRunDetails](GroupReconciliationRunDetails.md)
- [ResourceId](ResourceId.md)
- [GroupReconciliationInstanceId](GroupReconciliationInstanceId.md)
- [GroupReconciliationDates](GroupReconciliationDates.md)
- [Link](Link.md)
- [GroupReconciliationResultTypes](GroupReconciliationResultTypes.md)
- [GroupReconciliationResultStatuses](GroupReconciliationResultStatuses.md)
- [GroupReconciliationReviewStatuses](GroupReconciliationReviewStatuses.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

