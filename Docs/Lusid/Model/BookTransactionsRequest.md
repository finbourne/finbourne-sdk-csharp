# Finbourne.Sdk.Lusid.Model.BookTransactionsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AllocationIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | A collection of Allocation IDs |
| **TransactionProperties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | A collection of properties |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BookTransactionsRequest(
    allocationIds: new List<ResourceId>(),  // required — A collection of Allocation IDs
    transactionProperties: new PerpetualProperty(...)  // optional — A collection of properties
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BookTransactionsRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `AllocationIds`
- [PerpetualProperty](PerpetualProperty.md) — used in `TransactionProperties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

