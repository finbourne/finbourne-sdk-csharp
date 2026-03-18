# Finbourne.Sdk.Access.Model.EvaluationResponse

The result of an evaluation request
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Result** | **EvaluationResult** | Required | *No description available.* |
| **DetailedMessage** | **string** | Optional | In the case of the evaluation being denied a message may be returned |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new EvaluationResponse(
    result: ,  // required
    detailedMessage: "..."  // optional — In the case of the evaluation being denied a message may be returned
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EvaluationResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

