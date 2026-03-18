# Finbourne.Sdk.Lusid.Model.TransactionConfigurationTypeAlias

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The transaction type |
| **Description** | **string** | Required | Brief description of the transaction |
| **TransactionClass** | **string** | Required | Relates types of a similar class. E.g. Buy/Sell, StockIn/StockOut |
| **TransactionGroup** | **string** | Optional | Group is a set of codes related to a source, or sync. DEPRECATED: This field will be removed, use &#x60;Source&#x60; instead |
| **Source** | **string** | Optional | Used to group a set of transaction types |
| **TransactionRoles** | **string** | Required | . The available values are: None, LongLonger, LongShorter, ShortShorter, Shorter, ShortLonger, Longer, AllRoles |
| **IsDefault** | **bool** | Optional | IsDefault is a flag that denotes the default alias for a source. There can only be, at most, one per source. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionConfigurationTypeAlias(
    type: "...",  // required — The transaction type
    description: "...",  // required — Brief description of the transaction
    transactionClass: "...",  // required — Relates types of a similar class. E.g. Buy/Sell, StockIn/StockOut
    transactionGroup: "...",  // optional — Group is a set of codes related to a source, or sync. DEPRECATED: This field will be removed, use &#x60;Source&#x60; instead
    source: "...",  // optional — Used to group a set of transaction types
    transactionRoles: "...",  // required — . The available values are: None, LongLonger, LongShorter, ShortShorter, Shorter, ShortLonger, Longer, AllRoles
    isDefault: true  // optional — IsDefault is a flag that denotes the default alias for a source. There can only be, at most, one per source.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionConfigurationTypeAlias>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

