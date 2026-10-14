# Finbourne.Sdk.Identity.Model.ApiEndpoint

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Operation** | **string** | Optional | *No description available.* |
| **HttpMethod** | **string** | Required | *No description available.* |
| **Path** | **string** | Required | *No description available.* |
| **Status** | **string** | Optional | *No description available.* |
| **Summary** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new ApiEndpoint(
    operation: "...",  // optional
    httpMethod: "...",  // required
    path: "...",  // required
    status: "...",  // optional
    summary: "...",  // optional
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApiEndpoint>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

