# Finbourne.Sdk.Lusid.Model.RecApprovalDecision

An entry in the append-only log of approver decisions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApprovalCode** | **string** | Required | The approval slot this decision satisfies. Must match a required approval code. |
| **Decision** | **string** | Required | The decision made. Available values: Approve, RequestRevisions. |
| **Reason** | **string** | Optional | Rationale for the decision. |
| **UserId** | **string** | Required | The approver who made the decision. |
| **AsAtDecided** | **DateTimeOffset** | Required | The asAt datetime at which the decision was made. |
| **AsAtSuperseded** | **DateTimeOffset?** | Optional | The asAt datetime at which this entry was superseded. Null when it is the current standing entry. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecApprovalDecision(
    approvalCode: "...",  // required — The approval slot this decision satisfies. Must match a required approval code.
    decision: "...",  // required — The decision made. Available values: Approve, RequestRevisions.
    reason: "...",  // optional — Rationale for the decision.
    userId: "...",  // required — The approver who made the decision.
    asAtDecided: DateTimeOffset.Now,  // required — The asAt datetime at which the decision was made.
    asAtSuperseded: DateTimeOffset.Now  // optional — The asAt datetime at which this entry was superseded. Null when it is the current standing entry.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecApprovalDecision>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

