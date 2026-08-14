# Finbourne.Sdk.Lusid.Model.BatchReviewRecResultRequest

One item of a batch review request: applies review content to its targeted rec result(s). Exactly  one target, except FixAsGroup/ForceMatch which require two or more.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecResultIds** | **List&lt;string&gt;** | Required | The rec results targeted by this batch item. Exactly one, except FixAsGroup/ForceMatch which require two or more. |
| **Decision** | [RecResultDecisionUpdate](RecResultDecisionUpdate.md) | Optional | *No description available.* |
| **AssignedUser** | [RecResultAssignmentUpdate](RecResultAssignmentUpdate.md) | Optional | *No description available.* |
| **AssignedRole** | [RecResultAssignmentUpdate](RecResultAssignmentUpdate.md) | Optional | *No description available.* |
| **AddCommentText** | **string** | Optional | Optional comment text to add to each targeted result. |
| **Properties** | [List&lt;PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties in the RecResult domain. Filterable and sortable. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchReviewRecResultRequest(
    recResultIds: ,  // required — The rec results targeted by this batch item. Exactly one, except FixAsGroup/ForceMatch which require two or more.
    decision: new RecResultDecisionUpdate(...),  // optional
    assignedUser: new RecResultAssignmentUpdate(...),  // optional
    assignedRole: new RecResultAssignmentUpdate(...),  // optional
    addCommentText: "...",  // optional — Optional comment text to add to each targeted result.
    properties: new List<PerpetualProperty>()  // optional — Properties in the RecResult domain. Filterable and sortable.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchReviewRecResultRequest>(json);
```

- [RecResultDecisionUpdate](RecResultDecisionUpdate.md)
- [RecResultAssignmentUpdate](RecResultAssignmentUpdate.md)
- [RecResultAssignmentUpdate](RecResultAssignmentUpdate.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

