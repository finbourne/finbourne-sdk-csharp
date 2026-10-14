# Finbourne.Sdk.Workflow.Model.ServiceApiEndpoints

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Application** | **string** | Required | *No description available.* |
| **Endpoints** | [List&lt;ApiEndpoint&gt;](ApiEndpoint.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ServiceApiEndpoints(
    application: "...",  // required
    endpoints: new List<ApiEndpoint>(),  // required
    href: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ServiceApiEndpoints>(json);
```

- [ApiEndpoint](ApiEndpoint.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

