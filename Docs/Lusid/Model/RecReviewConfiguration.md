# Finbourne.Sdk.Lusid.Model.RecReviewConfiguration

How the results of a rec definition's runs are reviewed and approved: what needs reviewing, when the  reviewer may submit, and who has to approve the submission.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OpenExceptions** | [RecReviewRequirementRule](RecReviewRequirementRule.md) | Optional | *No description available.* |
| **ClosedExceptions** | [RecReviewRequirementRule](RecReviewRequirementRule.md) | Optional | *No description available.* |
| **Matches** | [RecReviewRequirementRule](RecReviewRequirementRule.md) | Optional | *No description available.* |
| **ReviewSubmission** | [RecReviewSubmission](RecReviewSubmission.md) | Optional | *No description available.* |
| **RequiredApprovals** | [List&lt;RecReviewRequiredApproval&gt;](RecReviewRequiredApproval.md) | Optional | The approvals a submitted review has to collect. All are required and may be given in any order, and no user may give more than one of them. Empty means no approvals are required and the reviewer self-approves on submission. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecReviewConfiguration(
    openExceptions: new RecReviewRequirementRule(...),  // optional
    closedExceptions: new RecReviewRequirementRule(...),  // optional
    matches: new RecReviewRequirementRule(...),  // optional
    reviewSubmission: new RecReviewSubmission(...),  // optional
    requiredApprovals: new List<RecReviewRequiredApproval>()  // optional — The approvals a submitted review has to collect. All are required and may be given in any order, and no user may give more than one of them. Empty means no approvals are required and the reviewer self-approves on submission.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecReviewConfiguration>(json);
```


## Related Models

- [RecReviewRequirementRule](RecReviewRequirementRule.md)
- [RecReviewRequirementRule](RecReviewRequirementRule.md)
- [RecReviewRequirementRule](RecReviewRequirementRule.md)
- [RecReviewSubmission](RecReviewSubmission.md)
- [RecReviewRequiredApproval](RecReviewRequiredApproval.md) — used in `RequiredApprovals`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

