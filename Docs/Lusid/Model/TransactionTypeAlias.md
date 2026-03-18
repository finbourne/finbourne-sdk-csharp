# Finbourne.Sdk.Lusid.Model.TransactionTypeAlias

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The transaction type |
| **Description** | **string** | Required | Brief description of the transaction |
| **TransactionClass** | **string** | Required | Relates types of a similar class. E.g. Buy/Sell, StockIn/StockOut |
| **TransactionRoles** | **string** | Required | Transactions role within a class. E.g. Increase a long position |
| **IsDefault** | **bool** | Optional | IsDefault is a flag that denotes the default alias for a source. There can only be, at most, one per source. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTypeAlias(
    type: "...",  // required — The transaction type
    description: "...",  // required — Brief description of the transaction
    transactionClass: "...",  // required — Relates types of a similar class. E.g. Buy/Sell, StockIn/StockOut
    transactionRoles: "...",  // required — Transactions role within a class. E.g. Increase a long position
    isDefault: true  // optional — IsDefault is a flag that denotes the default alias for a source. There can only be, at most, one per source.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTypeAlias>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

