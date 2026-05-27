# Finbourne.Sdk.Lusid.Model.NavSettlementConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CashSettlement** | [NavSettlementConfigurationCategory](NavSettlementConfigurationCategory.md) | Optional | *No description available.* |
| **DeferredCashReceipt** | [NavSettlementConfigurationCategory](NavSettlementConfigurationCategory.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NavSettlementConfiguration(
    cashSettlement: new NavSettlementConfigurationCategory(...),  // optional
    deferredCashReceipt: new NavSettlementConfigurationCategory(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NavSettlementConfiguration>(json);
```


## Related Models

- [NavSettlementConfigurationCategory](NavSettlementConfigurationCategory.md)
- [NavSettlementConfigurationCategory](NavSettlementConfigurationCategory.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

