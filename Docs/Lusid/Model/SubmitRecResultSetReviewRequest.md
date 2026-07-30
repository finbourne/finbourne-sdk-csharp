# Finbourne.Sdk.Lusid.Model.SubmitRecResultSetReviewRequest

The request to submit a result set review for approval (or resubmit after addressing revisions).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CommentText** | **string** | Optional | An optional comment recorded on the submission. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SubmitRecResultSetReviewRequest(
    commentText: "..."  // optional — An optional comment recorded on the submission.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SubmitRecResultSetReviewRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

