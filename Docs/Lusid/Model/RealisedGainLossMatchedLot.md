# Finbourne.Sdk.Lusid.Model.RealisedGainLossMatchedLot

The lot a realised chargeable-gains leg was matched against: its cost in the portfolio currency, the date of the  acquisition that opened it and its chargeable-gains role.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OriginalCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **PurchaseDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **Role** | **string** | Optional | Available values: DayLot, Section104Pool, Holding1982, Holding1965, FutureAcquisition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RealisedGainLossMatchedLot(
    originalCost: new CurrencyAndAmount(...),  // optional
    purchaseDate: DateTimeOffset.Now,  // optional
    role: "..."  // optional — Available values: DayLot, Section104Pool, Holding1982, Holding1965, FutureAcquisition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RealisedGainLossMatchedLot>(json);
```


## Related Models

- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

