# Finbourne.Sdk.Lusid.Model.AnnulStructuredDataResponse

The response to a request to annul (delete) a set of structured data from Lusid. This might have been for market data or some other structured entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | **Dictionary&lt;string, DateTimeOffset&gt;** | Optional | The set of values that were removed. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The set of values where removal failed, with a description as to why that is the case, e.g. badly formed request |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AnnulStructuredDataResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: ,  // optional — The set of values that were removed.
    failed: new ErrorDetail(...),  // optional — The set of values where removal failed, with a description as to why that is the case, e.g. badly formed request
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AnnulStructuredDataResponse>(json);
```

- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

