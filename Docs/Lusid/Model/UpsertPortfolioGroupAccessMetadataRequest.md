# Finbourne.Sdk.Lusid.Model.UpsertPortfolioGroupAccessMetadataRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Metadata** | [List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md) | Required | The access control metadata to assign to portfolio groups that match the identifier |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertPortfolioGroupAccessMetadataRequest(
    metadata: new List<AccessMetadataValue>()  // required — The access control metadata to assign to portfolio groups that match the identifier
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertPortfolioGroupAccessMetadataRequest>(json);
```


## Related Models

- [AccessMetadataValue](AccessMetadataValue.md) — used in `Metadata`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

