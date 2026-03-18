# Finbourne.Sdk.Lusid.Model.RealisedGainLoss

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies. |
| **InstrumentUid** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that this gain or loss is associated with. |
| **Units** | **decimal** | Required | The number of units of the associated instrument against which the gain or loss has been realised. |
| **PurchaseTradeDate** | **DateTimeOffset?** | Optional | The effective datetime at which the units associated with this gain or loss were originally purchased. *(read-only)* |
| **PurchaseSettlementDate** | **DateTimeOffset?** | Optional | The effective datetime at which the units associated with this gain or loss were originally settled. *(read-only)* |
| **PurchasePrice** | **decimal?** | Optional | The purchase price of each unit associated with this gain or loss. |
| **CostTradeCcy** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **CostPortfolioCcy** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **RealisedTradeCcy** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **RealisedTotal** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **RealisedMarket** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **RealisedCurrency** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **TaxLotId** | **string** | Optional | The identifier of the tax lot with which this gain or loss is associated. |
| **RealisedAmortisation** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **TradeDateToSettlementDateRealisedCurrency** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RealisedGainLoss(
    instrumentScope: "...",  // optional — The scope in which the instrument lies.
    instrumentUid: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that this gain or loss is associated with.
    units: 0.0d,  // required — The number of units of the associated instrument against which the gain or loss has been realised.
    purchaseTradeDate: DateTimeOffset.Now,  // optional — The effective datetime at which the units associated with this gain or loss were originally purchased.
    purchaseSettlementDate: DateTimeOffset.Now,  // optional — The effective datetime at which the units associated with this gain or loss were originally settled.
    purchasePrice: 0.0d,  // optional — The purchase price of each unit associated with this gain or loss.
    costTradeCcy: new CurrencyAndAmount(...),  // required
    costPortfolioCcy: new CurrencyAndAmount(...),  // required
    realisedTradeCcy: new CurrencyAndAmount(...),  // required
    realisedTotal: new CurrencyAndAmount(...),  // required
    realisedMarket: new CurrencyAndAmount(...),  // optional
    realisedCurrency: new CurrencyAndAmount(...),  // optional
    taxLotId: "...",  // optional — The identifier of the tax lot with which this gain or loss is associated.
    realisedAmortisation: new CurrencyAndAmount(...),  // optional
    tradeDateToSettlementDateRealisedCurrency: new CurrencyAndAmount(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RealisedGainLoss>(json);
```

- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

