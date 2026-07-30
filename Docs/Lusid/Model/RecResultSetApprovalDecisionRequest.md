# Finbourne.Sdk.Lusid.Model.RecResultSetApprovalDecisionRequest

The request for an approver to approve a submitted review or request revisions. Each call satisfies  (or rejects) one approval slot from the result set's required approvals.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApprovalCode** | **string** | Required | The approval slot being decided. Must match a required approval code. |
| **Decision** | **string** | Required | The decision made. Available values: Approve, RequestRevisions. |
| **Reason** | **string** | Optional | Rationale for the decision. |
| **RequestedResultRevisions** | [List&lt;RecRequestedResultRevision&gt;](RecRequestedResultRevision.md) | Optional | The results flagged for re-review. Only applicable when the decision is Request Revisions. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultSetApprovalDecisionRequest(
    approvalCode: "...",  // required — The approval slot being decided. Must match a required approval code.
    decision: "...",  // required — The decision made. Available values: Approve, RequestRevisions.
    reason: "...",  // optional — Rationale for the decision.
    requestedResultRevisions: new List<RecRequestedResultRevision>()  // optional — The results flagged for re-review. Only applicable when the decision is Request Revisions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultSetApprovalDecisionRequest>(json);
```

- [RecRequestedResultRevision](RecRequestedResultRevision.md) — used in `RequestedResultRevisions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

