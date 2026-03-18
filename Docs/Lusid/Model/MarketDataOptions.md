# Finbourne.Sdk.Lusid.Model.MarketDataOptions

Base class for representing market data options in LUSID.  Abstractly, these are any options that one should be able to specify for ComplexMarketData entities.  For example, CurveOptions allows one to decide how the data provided in a discountFactorCurve is interpolated.  This base class should not be directly instantiated;  each supported MarketDataOptionsType has a corresponding inherited class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketDataOptionsType** | **string** | Required | The available values are: CurveOptions |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarketDataOptions(
    marketDataOptionsType: "..."  // required — The available values are: CurveOptions
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarketDataOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

