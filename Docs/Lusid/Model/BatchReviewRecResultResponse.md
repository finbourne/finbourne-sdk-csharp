# Finbourne.Sdk.Lusid.Model.BatchReviewRecResultResponse

The response to a batch review request. Keyed by the client-supplied batch item key.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, BatchReviewRecResultItemResult&gt;](BatchReviewRecResultItemResult.md) | Required | The successfully-processed batch items, keyed by the client-supplied batch item key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The failed batch items, keyed by the client-supplied batch item key. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Response metadata, keyed by the client-supplied batch item key. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchReviewRecResultResponse(
    values: new BatchReviewRecResultItemResult(...),  // required — The successfully-processed batch items, keyed by the client-supplied batch item key.
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
var instance = JsonConvert.DeserializeObject<BatchReviewRecResultResponse>(json);
```


## Related Models

- [BatchReviewRecResultItemResult](BatchReviewRecResultItemResult.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

