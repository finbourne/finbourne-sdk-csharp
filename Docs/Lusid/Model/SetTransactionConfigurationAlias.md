# Finbourne.Sdk.Lusid.Model.SetTransactionConfigurationAlias

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **TransactionClass** | **string** | Required | *No description available.* |
| **TransactionRole** | **string** | Required | *No description available.* |
| **IsDefault** | **bool** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SetTransactionConfigurationAlias(
    type: "...",  // required
    description: "...",  // required
    transactionClass: "...",  // required
    transactionRole: "...",  // required
    isDefault: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetTransactionConfigurationAlias>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

