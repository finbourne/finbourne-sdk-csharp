# Finbourne.Sdk.Lusid.Model.SetTransactionConfigurationSourceRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Aliases** | [List&lt;SetTransactionConfigurationAlias&gt;](SetTransactionConfigurationAlias.md) | Required | *No description available.* |
| **Movements** | [List&lt;TransactionConfigurationMovementDataRequest&gt;](TransactionConfigurationMovementDataRequest.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SetTransactionConfigurationSourceRequest(
    aliases: new List<SetTransactionConfigurationAlias>(),  // required
    movements: new List<TransactionConfigurationMovementDataRequest>(),  // required
    properties: new PerpetualProperty(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetTransactionConfigurationSourceRequest>(json);
```


## Related Models

- [SetTransactionConfigurationAlias](SetTransactionConfigurationAlias.md)
- [TransactionConfigurationMovementDataRequest](TransactionConfigurationMovementDataRequest.md)
- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

