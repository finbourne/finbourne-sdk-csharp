# Finbourne.Sdk.Lusid.Model.RecResultLinkKey

One item pairing that established a link between two rec results: the identifiers both results' items carried.  Exactly one of holdingId and transactionId is populated; taxLotId only ever accompanies a holdingId, and only  where the pairing was established at tax-lot precision.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingId** | **string** | Optional | The holding both items carried, for a holding-keyed pairing. Null for a transaction-keyed one. |
| **TaxLotId** | **string** | Optional | The tax lot both items carried within the holding, where the pairing was established at tax-lot precision. Null where it was established at holding precision, and always null for a transaction-keyed pairing. |
| **TransactionId** | **string** | Optional | The transaction both items carried, for a transaction-keyed pairing. Null for a holding-keyed one. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultLinkKey(
    holdingId: "...",  // optional — The holding both items carried, for a holding-keyed pairing. Null for a transaction-keyed one.
    taxLotId: "...",  // optional — The tax lot both items carried within the holding, where the pairing was established at tax-lot precision. Null where it was established at holding precision, and always null for a transaction-keyed pairing.
    transactionId: "..."  // optional — The transaction both items carried, for a transaction-keyed pairing. Null for a holding-keyed one.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultLinkKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

