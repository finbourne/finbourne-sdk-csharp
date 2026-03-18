# Finbourne.Sdk.Workflow.Model.LusidValidationProblemDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **ErrorDetails** | **List&lt;Dictionary&lt;string, string&gt;&gt;** | Optional | *No description available.* |
| **Code** | **int** | Required | *No description available.* |
| **Errors** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | Optional | *No description available.* |
| **Type** | **string** | Optional | *No description available.* |
| **Title** | **string** | Optional | *No description available.* |
| **Status** | **int?** | Optional | *No description available.* |
| **Detail** | **string** | Optional | *No description available.* |
| **Instance** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LusidValidationProblemDetails(
    name: "...",  // required
    errorDetails: ,  // optional
    code: 0,  // required
    errors: ,  // optional
    type: "...",  // optional
    title: "...",  // optional
    status: 0,  // optional
    detail: "...",  // optional
    instance: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidValidationProblemDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

