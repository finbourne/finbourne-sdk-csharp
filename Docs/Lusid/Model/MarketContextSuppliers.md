# Finbourne.Sdk.Lusid.Model.MarketContextSuppliers

It is possible to control which supplier is used for a given asset class.  This field is deprecated in favour of market data rules, which subsumes its functionality.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Commodity** | **string** | Optional | *No description available.* |
| **Credit** | **string** | Optional | *No description available.* |
| **Equity** | **string** | Optional | *No description available.* |
| **Fx** | **string** | Optional | *No description available.* |
| **Rates** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarketContextSuppliers(
    commodity: "...",  // optional
    credit: "...",  // optional
    equity: "...",  // optional
    fx: "...",  // optional
    rates: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarketContextSuppliers>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

