# Finbourne.Sdk.Lusid.Model.RecSubmission

An entry in the append-only log of review submissions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UserId** | **string** | Required | The user who submitted the review. |
| **CommentText** | **string** | Optional | An optional comment from the submitter. |
| **AsAtSubmitted** | **DateTimeOffset** | Required | The asAt datetime at which the submission was made. |
| **AsAtSuperseded** | **DateTimeOffset?** | Optional | The asAt datetime at which this entry was superseded. Null when it is the current standing entry. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecSubmission(
    userId: "...",  // required — The user who submitted the review.
    commentText: "...",  // optional — An optional comment from the submitter.
    asAtSubmitted: DateTimeOffset.Now,  // required — The asAt datetime at which the submission was made.
    asAtSuperseded: DateTimeOffset.Now  // optional — The asAt datetime at which this entry was superseded. Null when it is the current standing entry.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecSubmission>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

