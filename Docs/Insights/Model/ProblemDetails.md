# Finbourne.Sdk.Insights.Model.ProblemDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | *No description available.* |
| **Title** | **string** | Optional | *No description available.* |
| **Status** | **int?** | Optional | *No description available.* |
| **Detail** | **string** | Optional | *No description available.* |
| **Instance** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ProblemDetails(
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
var instance = JsonConvert.DeserializeObject<ProblemDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

