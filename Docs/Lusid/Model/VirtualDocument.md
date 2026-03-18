# Finbourne.Sdk.Lusid.Model.VirtualDocument

Virtual document consists of (potentially several) upserted documents.                The documents get parsed according to the provided data map on upsert, the collection of resulting values in  aggregated in a virtual document
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DocumentId** | [StructuredResultDataId](StructuredResultDataId.md) | Optional | *No description available.* |
| **Data** | [List&lt;VirtualDocumentRow&gt;](VirtualDocumentRow.md) | Optional | The data inside the document |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VirtualDocument(
    documentId: new StructuredResultDataId(...),  // optional
    data: new List<VirtualDocumentRow>()  // optional — The data inside the document
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VirtualDocument>(json);
```


## Related Models

- [StructuredResultDataId](StructuredResultDataId.md)
- [VirtualDocumentRow](VirtualDocumentRow.md) — used in `Data`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

