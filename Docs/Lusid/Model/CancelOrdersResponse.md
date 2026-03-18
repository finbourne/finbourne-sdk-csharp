# Finbourne.Sdk.Lusid.Model.CancelOrdersResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, CancelledOrderResult&gt;](CancelledOrderResult.md) | Optional | The orders which have been successfully cancelled. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The orders that could not be cancelled, along with a reason for their failure. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Meta data associated with the cancellation event. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelOrdersResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new CancelledOrderResult(...),  // optional — The orders which have been successfully cancelled.
    failed: new ErrorDetail(...),  // optional — The orders that could not be cancelled, along with a reason for their failure.
    metadata: ,  // optional — Meta data associated with the cancellation event.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelOrdersResponse>(json);
```

- [CancelledOrderResult](CancelledOrderResult.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

