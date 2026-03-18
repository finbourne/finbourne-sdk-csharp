# Finbourne.Sdk.Lusid.Model.TransactionTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Aliases** | [List&lt;TransactionTypeAlias&gt;](TransactionTypeAlias.md) | Required | List of transaction types that map to this specific transaction configuration |
| **Movements** | [List&lt;TransactionTypeMovement&gt;](TransactionTypeMovement.md) | Required | Movement data for the transaction type |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties attached to the transaction type |
| **Calculations** | [List&lt;TransactionTypeCalculation&gt;](TransactionTypeCalculation.md) | Optional | Calculations to be performed for the transaction type |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTypeRequest(
    aliases: new List<TransactionTypeAlias>(),  // required — List of transaction types that map to this specific transaction configuration
    movements: new List<TransactionTypeMovement>(),  // required — Movement data for the transaction type
    properties: new PerpetualProperty(...),  // optional — Properties attached to the transaction type
    calculations: new List<TransactionTypeCalculation>()  // optional — Calculations to be performed for the transaction type
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTypeRequest>(json);
```


## Related Models

- [TransactionTypeAlias](TransactionTypeAlias.md) — used in `Aliases`
- [TransactionTypeMovement](TransactionTypeMovement.md) — used in `Movements`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [TransactionTypeCalculation](TransactionTypeCalculation.md) — used in `Calculations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

