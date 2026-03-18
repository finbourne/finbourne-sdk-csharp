# Finbourne.Sdk.Luminesce.Model.BackgroundMultiQueryProgressResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Progress** | **string** | Optional | The full progress log (up to this point at least) |
| **Feedback** | [List&lt;FeedbackEventArgs&gt;](FeedbackEventArgs.md) | Optional | Individual Feedback Messages (to replace Progress).  A given message will be returned from only one call. |
| **Status** | **TaskStatus** | Optional | *No description available.* |
| **Queries** | [List&lt;BackgroundQueryProgressResponse&gt;](BackgroundQueryProgressResponse.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new BackgroundMultiQueryProgressResponse(
    progress: "...",  // optional — The full progress log (up to this point at least)
    feedback: new List<FeedbackEventArgs>(),  // optional — Individual Feedback Messages (to replace Progress).  A given message will be returned from only one call.
    status: ,  // optional
    queries: new List<BackgroundQueryProgressResponse>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BackgroundMultiQueryProgressResponse>(json);
```

- [FeedbackEventArgs](FeedbackEventArgs.md) — used in `Feedback`
- [BackgroundQueryProgressResponse](BackgroundQueryProgressResponse.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

