# Finbourne.Sdk.Lusid.Model.BatchUpsertPortfolioAccessMetadataResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, BatchUpsertPortfolioAccessMetadataResponseItem&gt;](BatchUpsertPortfolioAccessMetadataResponseItem.md) | Optional | The items have been successfully updated or created. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The items that could not be updated or created along with a reason for their failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpsertPortfolioAccessMetadataResponse(
    values: new BatchUpsertPortfolioAccessMetadataResponseItem(...),  // optional — The items have been successfully updated or created.
    failed: new ErrorDetail(...),  // optional — The items that could not be updated or created along with a reason for their failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpsertPortfolioAccessMetadataResponse>(json);
```


## Related Models

- [BatchUpsertPortfolioAccessMetadataResponseItem](BatchUpsertPortfolioAccessMetadataResponseItem.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

