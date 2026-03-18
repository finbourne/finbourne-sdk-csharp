# Finbourne.Sdk.Lusid.Model.GetVirtualDocumentResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, VirtualDocument&gt;](VirtualDocument.md) | Optional | The set of values that were successfully retrieved. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The set of calues that could not be retrieved along with a reason for this, e.g. badly formed request. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetVirtualDocumentResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new VirtualDocument(...),  // optional — The set of values that were successfully retrieved.
    failed: new ErrorDetail(...),  // optional — The set of calues that could not be retrieved along with a reason for this, e.g. badly formed request.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetVirtualDocumentResponse>(json);
```

- [VirtualDocument](VirtualDocument.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

