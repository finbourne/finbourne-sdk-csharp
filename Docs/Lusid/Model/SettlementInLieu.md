# Finbourne.Sdk.Lusid.Model.SettlementInLieu

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OriginalSettlementCurrency** | **string** | Required | *No description available.* |
| **Amount** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementInLieu(
    originalSettlementCurrency: "...",  // required
    amount: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementInLieu>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

