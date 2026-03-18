# Finbourne.Sdk.Lusid.Model.ReconciliationTransactions

Specification for the transactions of a scheduled reconciliation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionWindow** | [DateRange](DateRange.md) | Optional | *No description available.* |
| **MappingId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationTransactions(
    transactionWindow: new DateRange(...),  // optional
    mappingId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationTransactions>(json);
```


## Related Models

- [DateRange](DateRange.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

