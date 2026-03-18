# Finbourne.Sdk.Lusid.Model.MultiCurrencyAmounts

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LocalAmount** | **decimal** | Required | *No description available.* |
| **BaseAmount** | **decimal** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MultiCurrencyAmounts(
    localAmount: 0.0d,  // required
    baseAmount: 0.0d  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MultiCurrencyAmounts>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

