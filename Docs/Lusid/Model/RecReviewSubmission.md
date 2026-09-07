# Finbourne.Sdk.Lusid.Model.RecReviewSubmission

When the reviewer is allowed to submit their work for approval. Omit it to let them submit at any time.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CompletionRatioThreshold** | **decimal** | Required | The review completion ratio a result set has to reach before it can be submitted, between 0.0 and 1.0 inclusive. |
| **AutoSubmit** | **bool** | Optional | Whether the system submits on the reviewer&#39;s behalf as soon as the completion ratio threshold is met, rather than waiting to be asked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecReviewSubmission(
    completionRatioThreshold: 0.0d,  // required — The review completion ratio a result set has to reach before it can be submitted, between 0.0 and 1.0 inclusive.
    autoSubmit: true  // optional — Whether the system submits on the reviewer&#39;s behalf as soon as the completion ratio threshold is met, rather than waiting to be asked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecReviewSubmission>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

