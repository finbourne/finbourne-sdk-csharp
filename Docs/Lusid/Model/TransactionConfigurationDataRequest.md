# Finbourne.Sdk.Lusid.Model.TransactionConfigurationDataRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Aliases** | [List&lt;TransactionConfigurationTypeAlias&gt;](TransactionConfigurationTypeAlias.md) | Required | List of transaction codes that map to this specific transaction model |
| **Movements** | [List&lt;TransactionConfigurationMovementDataRequest&gt;](TransactionConfigurationMovementDataRequest.md) | Required | Movement data for the transaction code |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties attached to the underlying holding. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionConfigurationDataRequest(
    aliases: new List<TransactionConfigurationTypeAlias>(),  // required — List of transaction codes that map to this specific transaction model
    movements: new List<TransactionConfigurationMovementDataRequest>(),  // required — Movement data for the transaction code
    properties: new PerpetualProperty(...)  // optional — Properties attached to the underlying holding.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionConfigurationDataRequest>(json);
```


## Related Models

- [TransactionConfigurationTypeAlias](TransactionConfigurationTypeAlias.md) — used in `Aliases`
- [TransactionConfigurationMovementDataRequest](TransactionConfigurationMovementDataRequest.md) — used in `Movements`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

