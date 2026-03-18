# Finbourne.Sdk.Lusid.Model.TransactionConfigurationData

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Aliases** | [List&lt;TransactionConfigurationTypeAlias&gt;](TransactionConfigurationTypeAlias.md) | Required | List of transaction types that map to this specific transaction configuration |
| **Movements** | [List&lt;TransactionConfigurationMovementData&gt;](TransactionConfigurationMovementData.md) | Required | Movement data for the transaction type |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties attached to the transaction type |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionConfigurationData(
    aliases: new List<TransactionConfigurationTypeAlias>(),  // required — List of transaction types that map to this specific transaction configuration
    movements: new List<TransactionConfigurationMovementData>(),  // required — Movement data for the transaction type
    properties: new PerpetualProperty(...)  // optional — Properties attached to the transaction type
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionConfigurationData>(json);
```


## Related Models

- [TransactionConfigurationTypeAlias](TransactionConfigurationTypeAlias.md) — used in `Aliases`
- [TransactionConfigurationMovementData](TransactionConfigurationMovementData.md) — used in `Movements`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

