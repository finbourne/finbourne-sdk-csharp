# Finbourne.Sdk.Luminesce.Model.FeedbackEventArgs

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **When** | **DateTimeOffset** | Optional | *No description available.* |
| **SessionId** | **Guid** | Optional | *No description available.* |
| **ExecutionId** | **Guid** | Optional | *No description available.* |
| **Level** | **FeedbackLevel** | Optional | *No description available.* |
| **Sender** | **string** | Optional | *No description available.* |
| **StateId** | **int?** | Optional | *No description available.* |
| **MessageTemplate** | **string** | Optional | *No description available.* |
| **PropertyValues** | **List&lt;Object&gt;** | Optional | *No description available.* |
| **Message** | **string** | Optional | *No description available.* *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new FeedbackEventArgs(
    when: DateTimeOffset.Now,  // optional
    sessionId: "...",  // optional
    executionId: "...",  // optional
    level: ,  // optional
    sender: "...",  // optional
    stateId: 0,  // optional
    messageTemplate: "...",  // optional
    propertyValues: ,  // optional
    message: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeedbackEventArgs>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

