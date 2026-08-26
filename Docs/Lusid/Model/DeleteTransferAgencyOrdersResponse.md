# Finbourne.Sdk.Lusid.Model.DeleteTransferAgencyOrdersResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Successes** | [Dictionary&lt;string, DeleteTransferAgencyOrderResult&gt;](DeleteTransferAgencyOrderResult.md) | Optional | A dictionary of successfully deleted orders, keyed by the request key. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | A dictionary of failed order deletion attempts, keyed by the request key, containing error details. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteTransferAgencyOrdersResponse(
    successes: new DeleteTransferAgencyOrderResult(...),  // optional — A dictionary of successfully deleted orders, keyed by the request key.
    failed: new ErrorDetail(...),  // optional — A dictionary of failed order deletion attempts, keyed by the request key, containing error details.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteTransferAgencyOrdersResponse>(json);
```


## Related Models

- [DeleteTransferAgencyOrderResult](DeleteTransferAgencyOrderResult.md) — used in `Successes`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

