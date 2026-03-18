# Finbourne.Sdk.Lusid.Model.BatchUpsertPortfolioAccessMetadataResponseItem

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Metadata** | **Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BatchUpsertPortfolioAccessMetadataResponseItem(
    portfolioId: new ResourceId(...),  // required
    metadata:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpsertPortfolioAccessMetadataResponseItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

