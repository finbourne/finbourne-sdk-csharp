# Finbourne.Sdk.Lusid.Model.GetFlowConventionsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Value** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The identifiers that did not resolve to a conventions along with the nature of the failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetFlowConventionsResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    value: new FlowConventions(...),  // optional
    failed: new ErrorDetail(...),  // optional — The identifiers that did not resolve to a conventions along with the nature of the failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetFlowConventionsResponse>(json);
```

- [FlowConventions](FlowConventions.md)
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

