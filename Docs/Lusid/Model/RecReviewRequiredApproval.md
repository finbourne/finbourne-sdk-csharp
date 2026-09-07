# Finbourne.Sdk.Lusid.Model.RecReviewRequiredApproval

One approval a submitted review has to collect, and who may give it. All of a configuration's approvals are  required, they may be given in any order, and no user may give more than one of them.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ApprovalCode** | **string** | Required | The client-defined identifier for the approval, e.g. \&quot;Desk\&quot; or \&quot;Risk\&quot;. Each may appear at most once. |
| **Description** | **string** | Optional | A human-readable label for the approval. |
| **DecidingUser** | **string** | Optional | A boolean expression over the user attempting the approval, which has to hold for them to give it. They must also hold the entitlement for the decide action. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecReviewRequiredApproval(
    approvalCode: "...",  // required — The client-defined identifier for the approval, e.g. \&quot;Desk\&quot; or \&quot;Risk\&quot;. Each may appear at most once.
    description: "...",  // optional — A human-readable label for the approval.
    decidingUser: "..."  // optional — A boolean expression over the user attempting the approval, which has to hold for them to give it. They must also hold the entitlement for the decide action.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecReviewRequiredApproval>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

