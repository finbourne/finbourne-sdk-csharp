# Finbourne.Sdk.Lusid.Model.ServiceApiEndpoints

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Application** | **string** | Required | *No description available.* |
| **Endpoints** | [List&lt;ApiEndpoint&gt;](ApiEndpoint.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ServiceApiEndpoints(
    application: "...",  // required
    endpoints: new List<ApiEndpoint>(),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
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

