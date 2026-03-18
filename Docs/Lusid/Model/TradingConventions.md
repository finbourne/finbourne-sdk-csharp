# Finbourne.Sdk.Lusid.Model.TradingConventions

Common Trading details for exchange traded instruments like Futures and Bonds
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PriceScaleFactor** | **decimal** | Optional | The factor used to scale prices for the instrument. Currently used by LUSID when calculating cost  and notional amounts on transactions. Note this factor does not yet impact Valuation, PV, exposure,  all of which use the scale factor attached to the price quotes in the QuoteStore.  Must be positive and defaults to 1 if not set. |
| **MinimumOrderSize** | **decimal** | Optional | The Minimum Order Size  Must be non-negative and defaults to 0 if not set. |
| **MinimumOrderIncrement** | **decimal** | Optional | The Minimum Order Increment  Must be non-negative and defaults to 0 if not set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TradingConventions(
    priceScaleFactor: 0.0d,  // optional — The factor used to scale prices for the instrument. Currently used by LUSID when calculating cost  and notional amounts on transactions. Note this factor does not yet impact Valuation, PV, exposure,  all of which use the scale factor attached to the price quotes in the QuoteStore.  Must be positive and defaults to 1 if not set.
    minimumOrderSize: 0.0d,  // optional — The Minimum Order Size  Must be non-negative and defaults to 0 if not set.
    minimumOrderIncrement: 0.0d  // optional — The Minimum Order Increment  Must be non-negative and defaults to 0 if not set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TradingConventions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

