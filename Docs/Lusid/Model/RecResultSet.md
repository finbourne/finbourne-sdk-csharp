# Finbourne.Sdk.Lusid.Model.RecResultSet

The collection of reconciliation results for a given rec type within a rec instance. Identified by  its rec type and instance. The latest run's data is promoted to the root; prior runs are available  via previousRuns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecType** | **string** | Required | The type of rec that this result set belongs to (e.g. Holding). Together with the rec instance, this uniquely identifies the result set. Available values: Holding, Transaction, Valuation, CashHolding. |
| **RecInstance** | [RecInstanceSummary](RecInstanceSummary.md) | Required | *No description available.* |
| **RunNumber** | **int** | Required | The run number within the instance. Increments with each re-run. |
| **RunAsAt** | **DateTimeOffset** | Required | The asAt datetime at which the run happened. |
| **Execution** | [RecExecution](RecExecution.md) | Required | *No description available.* |
| **DatesReconciled** | [RecDatesReconciled](RecDatesReconciled.md) | Required | *No description available.* |
| **ResultCounts** | [RecResultCounts](RecResultCounts.md) | Required | *No description available.* |
| **Review** | [RecReview](RecReview.md) | Required | *No description available.* |
| **ApprovalStatus** | **string** | Required | The position of this result set in the approval ceremony. Available values: UnderReview, PendingApproval, RevisionsRequested, Approved, NotApplicable. |
| **RequiredApprovals** | [List&lt;RecRequiredApproval&gt;](RecRequiredApproval.md) | Required | The approval slots required for this result set, passed through from the rec definition&#39;s review configuration. May be empty. |
| **Submissions** | [List&lt;RecSubmission&gt;](RecSubmission.md) | Required | An append-only log of review submissions. May be empty. |
| **Decisions** | [List&lt;RecApprovalDecision&gt;](RecApprovalDecision.md) | Required | An append-only log of approver decisions. May be empty. |
| **PreviousRuns** | [List&lt;RecSupersededRun&gt;](RecSupersededRun.md) | Required | Prior run snapshots, each frozen at the point of re-run. Populated only when includePreviousRuns is true. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultSet(
    recType: "...",  // required — The type of rec that this result set belongs to (e.g. Holding). Together with the rec instance, this uniquely identifies the result set. Available values: Holding, Transaction, Valuation, CashHolding.
    recInstance: new RecInstanceSummary(...),  // required
    runNumber: 0,  // required — The run number within the instance. Increments with each re-run.
    runAsAt: DateTimeOffset.Now,  // required — The asAt datetime at which the run happened.
    execution: new RecExecution(...),  // required
    datesReconciled: new RecDatesReconciled(...),  // required
    resultCounts: new RecResultCounts(...),  // required
    review: new RecReview(...),  // required
    approvalStatus: "...",  // required — The position of this result set in the approval ceremony. Available values: UnderReview, PendingApproval, RevisionsRequested, Approved, NotApplicable.
    requiredApprovals: new List<RecRequiredApproval>(),  // required — The approval slots required for this result set, passed through from the rec definition&#39;s review configuration. May be empty.
    submissions: new List<RecSubmission>(),  // required — An append-only log of review submissions. May be empty.
    decisions: new List<RecApprovalDecision>(),  // required — An append-only log of approver decisions. May be empty.
    previousRuns: new List<RecSupersededRun>(),  // required — Prior run snapshots, each frozen at the point of re-run. Populated only when includePreviousRuns is true.
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
var instance = JsonConvert.DeserializeObject<RecResultSet>(json);
```

- [RecInstanceSummary](RecInstanceSummary.md)
- [RecExecution](RecExecution.md)
- [RecDatesReconciled](RecDatesReconciled.md)
- [RecResultCounts](RecResultCounts.md)
- [RecReview](RecReview.md)
- [RecRequiredApproval](RecRequiredApproval.md) — used in `RequiredApprovals`
- [RecSubmission](RecSubmission.md) — used in `Submissions`
- [RecApprovalDecision](RecApprovalDecision.md) — used in `Decisions`
- [RecSupersededRun](RecSupersededRun.md) — used in `PreviousRuns`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

