# Finbourne.Sdk.Lusid.Model.GetQuotesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, Quote&gt;](Quote.md) | Optional | The quotes which have been successfully retrieved. |
| **NotFound** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The quotes that could not be found along with a reason why. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The quotes that could not be retrieved due to an error along with a reason for their failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetQuotesResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new Quote(...),  // optional — The quotes which have been successfully retrieved.
    notFound: new ErrorDetail(...),  // optional — The quotes that could not be found along with a reason why.
    failed: new ErrorDetail(...),  // optional — The quotes that could not be retrieved due to an error along with a reason for their failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetQuotesResponse>(json);
```

- [Quote](Quote.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `NotFound`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

