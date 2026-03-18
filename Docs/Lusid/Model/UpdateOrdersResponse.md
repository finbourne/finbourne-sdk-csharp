# Finbourne.Sdk.Lusid.Model.UpdateOrdersResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Values** | [Dictionary&lt;string, Order&gt;](Order.md) | Optional | The orders which have been successfully updated. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The orders that could not be updated, along with a reason for their failure. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Meta data associated with the update event. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateOrdersResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    values: new Order(...),  // optional — The orders which have been successfully updated.
    failed: new ErrorDetail(...),  // optional — The orders that could not be updated, along with a reason for their failure.
    metadata: ,  // optional — Meta data associated with the update event.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateOrdersResponse>(json);
```

- [Order](Order.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

