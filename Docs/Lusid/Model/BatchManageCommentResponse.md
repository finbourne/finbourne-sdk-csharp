# Finbourne.Sdk.Lusid.Model.BatchManageCommentResponse

The response to a batch manage-comments request. Keyed by the client-supplied batch item key; each  success returns the full updated rec result.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, RecResult&gt;](RecResult.md) | Required | The successfully-processed batch items, keyed by the client-supplied batch item key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The failed batch items, keyed by the client-supplied batch item key. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Response metadata, keyed by the client-supplied batch item key. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchManageCommentResponse(
    values: new RecResult(...),  // required — The successfully-processed batch items, keyed by the client-supplied batch item key.
    failed: new ErrorDetail(...),  // optional — The failed batch items, keyed by the client-supplied batch item key.
    metadata: ,  // optional — Response metadata, keyed by the client-supplied batch item key.
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
var instance = JsonConvert.DeserializeObject<BatchManageCommentResponse>(json);
```


## Related Models

- [RecResult](RecResult.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

