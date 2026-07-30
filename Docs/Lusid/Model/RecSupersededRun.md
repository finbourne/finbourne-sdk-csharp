# Finbourne.Sdk.Lusid.Model.RecSupersededRun

A prior run snapshot, frozen at the point of re-run. Has the same shape as the root-level run  fields on the result set, plus the asAt at which the run was superseded.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunNumber** | **int** | Required | The run number within the instance. Increments with each re-run. |
| **RunAsAt** | **DateTimeOffset** | Required | The asAt datetime at which the run happened. |
| **SupersededAsAt** | **DateTimeOffset** | Required | The asAt datetime at which this run was superseded by a subsequent run. |
| **Execution** | [RecExecution](RecExecution.md) | Required | *No description available.* |
| **DatesReconciled** | [RecDatesReconciled](RecDatesReconciled.md) | Required | *No description available.* |
| **ResultCounts** | [RecResultCounts](RecResultCounts.md) | Required | *No description available.* |
| **Review** | [RecReview](RecReview.md) | Required | *No description available.* |
| **ApprovalStatus** | **string** | Required | The position of this result set in the approval ceremony. Available values: UnderReview, PendingApproval, RevisionsRequested, Approved, NotApplicable. |
| **RequiredApprovals** | [List&lt;RecRequiredApproval&gt;](RecRequiredApproval.md) | Required | The approval slots required for this result set, passed through from the rec definition&#39;s review configuration. May be empty. |
| **Submissions** | [List&lt;RecSubmission&gt;](RecSubmission.md) | Required | An append-only log of review submissions. May be empty. |
| **Decisions** | [List&lt;RecApprovalDecision&gt;](RecApprovalDecision.md) | Required | An append-only log of approver decisions. May be empty. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecSupersededRun(
    runNumber: 0,  // required — The run number within the instance. Increments with each re-run.
    runAsAt: DateTimeOffset.Now,  // required — The asAt datetime at which the run happened.
    supersededAsAt: DateTimeOffset.Now,  // required — The asAt datetime at which this run was superseded by a subsequent run.
    execution: new RecExecution(...),  // required
    datesReconciled: new RecDatesReconciled(...),  // required
    resultCounts: new RecResultCounts(...),  // required
    review: new RecReview(...),  // required
    approvalStatus: "...",  // required — The position of this result set in the approval ceremony. Available values: UnderReview, PendingApproval, RevisionsRequested, Approved, NotApplicable.
    requiredApprovals: new List<RecRequiredApproval>(),  // required — The approval slots required for this result set, passed through from the rec definition&#39;s review configuration. May be empty.
    submissions: new List<RecSubmission>(),  // required — An append-only log of review submissions. May be empty.
    decisions: new List<RecApprovalDecision>()  // required — An append-only log of approver decisions. May be empty.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecSupersededRun>(json);
```

- [RecExecution](RecExecution.md)
- [RecDatesReconciled](RecDatesReconciled.md)
- [RecResultCounts](RecResultCounts.md)
- [RecReview](RecReview.md)
- [RecRequiredApproval](RecRequiredApproval.md) — used in `RequiredApprovals`
- [RecSubmission](RecSubmission.md) — used in `Submissions`
- [RecApprovalDecision](RecApprovalDecision.md) — used in `Decisions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

