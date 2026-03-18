# Finbourne.Sdk.Lusid.Model.ComponentTransaction

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | *No description available.* |
| **Condition** | **string** | Optional | *No description available.* |
| **TransactionFieldMap** | [TransactionFieldMap](TransactionFieldMap.md) | Required | *No description available.* |
| **TransactionPropertyMap** | [List&lt;TransactionPropertyMap&gt;](TransactionPropertyMap.md) | Required | *No description available.* |
| **PreserveTaxLotStructure** | **bool?** | Optional | Controls if tax lot structure should be preserved when cost base is transferred to a new holding. For example in Spin Off instrument events. |
| **MarketOpenTimeAdjustments** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComponentTransaction(
    displayName: "...",  // required
    condition: "...",  // optional
    transactionFieldMap: new TransactionFieldMap(...),  // required
    transactionPropertyMap: new List<TransactionPropertyMap>(),  // required
    preserveTaxLotStructure: true,  // optional — Controls if tax lot structure should be preserved when cost base is transferred to a new holding. For example in Spin Off instrument events.
    marketOpenTimeAdjustments:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComponentTransaction>(json);
```

- [TransactionFieldMap](TransactionFieldMap.md)
- [TransactionPropertyMap](TransactionPropertyMap.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

