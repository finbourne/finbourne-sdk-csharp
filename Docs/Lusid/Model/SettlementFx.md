# Finbourne.Sdk.Lusid.Model.SettlementFx

The FX gain or loss on a settlement instruction, with its transaction's realised gain or loss.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementCurrency** | **string** | Optional | *No description available.* |
| **SettlementAmount** | **decimal** | Optional | *No description available.* |
| **PortfolioCurrencyAmount** | **decimal?** | Optional | *No description available.* |
| **TradeDateFxRate** | **decimal?** | Optional | *No description available.* |
| **FxRateUsed** | **decimal?** | Optional | *No description available.* |
| **FxRateSource** | **string** | Optional | *No description available.* |
| **FxGainLossOnSettlement** | **decimal?** | Optional | *No description available.* |
| **TotalRealisedGainLossOnTransaction** | **decimal** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementFx(
    settlementCurrency: "...",  // optional
    settlementAmount: 0.0d,  // optional
    portfolioCurrencyAmount: 0.0d,  // optional
    tradeDateFxRate: 0.0d,  // optional
    fxRateUsed: 0.0d,  // optional
    fxRateSource: "...",  // optional
    fxGainLossOnSettlement: 0.0d,  // optional
    totalRealisedGainLossOnTransaction: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementFx>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

