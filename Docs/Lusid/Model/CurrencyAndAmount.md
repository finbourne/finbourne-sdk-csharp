# Finbourne.Sdk.Lusid.Model.CurrencyAndAmount

An amount of a specific currency, specifying a value and an associated unit
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Optional | *No description available.* |
| **Currency** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CurrencyAndAmount(
    amount: 0.0d,  // optional
    currency: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CurrencyAndAmount>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

