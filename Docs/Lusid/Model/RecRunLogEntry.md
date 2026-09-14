# Finbourne.Sdk.Lusid.Model.RecRunLogEntry

A summary of a single run of a single rec type within an instance's run log, carrying the per-run outcome  detail the grouped-by-instance overview renders. Every entry comes off a result set, so only a run that has  completed or failed appears: a run still in flight is not logged until it lands.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunNumber** | **int** | Required | The run number within the instance. Increments with each re-run. |
| **RunAsAt** | **DateTimeOffset** | Required | The asAt datetime at which the run happened. |
| **SupersededAsAt** | **DateTimeOffset?** | Optional | The asAt datetime at which this run was superseded by a subsequent run. |
| **DatesReconciled** | [RecDatesReconciled](RecDatesReconciled.md) | Required | *No description available.* |
| **Execution** | [RecExecution](RecExecution.md) | Required | *No description available.* |
| **ApprovalStatus** | **string** | Required | The position of this result set in the approval ceremony. Available values: UnderReview, PendingApproval, RevisionsRequested, Approved, NotApplicable. |
| **ResultCounts** | [RecResultCounts](RecResultCounts.md) | Optional | *No description available.* |
| **Review** | [RecReview](RecReview.md) | Optional | *No description available.* |
| **RecResultSetHref** | **string** | Required | The specific Uniform Resource Identifier (URI) of the full rec result set this run belongs to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecRunLogEntry(
    runNumber: 0,  // required — The run number within the instance. Increments with each re-run.
    runAsAt: DateTimeOffset.Now,  // required — The asAt datetime at which the run happened.
    supersededAsAt: DateTimeOffset.Now,  // optional — The asAt datetime at which this run was superseded by a subsequent run.
    datesReconciled: new RecDatesReconciled(...),  // required
    execution: new RecExecution(...),  // required
    approvalStatus: "...",  // required — The position of this result set in the approval ceremony. Available values: UnderReview, PendingApproval, RevisionsRequested, Approved, NotApplicable.
    resultCounts: new RecResultCounts(...),  // optional
    review: new RecReview(...),  // optional
    recResultSetHref: "..."  // required — The specific Uniform Resource Identifier (URI) of the full rec result set this run belongs to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecRunLogEntry>(json);
```

- [RecDatesReconciled](RecDatesReconciled.md)
- [RecExecution](RecExecution.md)
- [RecResultCounts](RecResultCounts.md)
- [RecReview](RecReview.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

