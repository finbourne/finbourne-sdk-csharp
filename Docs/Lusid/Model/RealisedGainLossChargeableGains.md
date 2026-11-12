# Finbourne.Sdk.Lusid.Model.RealisedGainLossChargeableGains

The UK chargeable-gains figures the engine worked for a realised-gain/loss leg: the chargeable gain, the  indexation allowance and the part of it taken, the proceeds the leg was worked on, both sides of the s.35  kink test on a 1982 holding, the basis and identification rule the leg was matched under, the lot it was  matched against, whether its transaction stands reversed, and the treatment applied. All amounts are in  the portfolio currency.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ChargeableGain** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **IndexationAllowance** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **IndexationAllowanceTaken** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Proceeds** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **GainOnOriginalCost** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **GainOnMarketValue1982** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Basis** | **string** | Optional | Available values: IndexedCost, MarketValue1982, OriginalCost, NilGain. |
| **MatchRule** | **string** | Optional | Available values: SameDay, TenDay, Section210B, Section104Pool, Holding1982, Holding1965. |
| **MatchedLot** | [RealisedGainLossMatchedLot](RealisedGainLossMatchedLot.md) | Optional | *No description available.* |
| **MarketValue1965** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Reversed** | **bool** | Optional | *No description available.* |
| **TaxTreatment** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RealisedGainLossChargeableGains(
    chargeableGain: new CurrencyAndAmount(...),  // optional
    indexationAllowance: new CurrencyAndAmount(...),  // optional
    indexationAllowanceTaken: new CurrencyAndAmount(...),  // optional
    proceeds: new CurrencyAndAmount(...),  // optional
    gainOnOriginalCost: new CurrencyAndAmount(...),  // optional
    gainOnMarketValue1982: new CurrencyAndAmount(...),  // optional
    basis: "...",  // optional — Available values: IndexedCost, MarketValue1982, OriginalCost, NilGain.
    matchRule: "...",  // optional — Available values: SameDay, TenDay, Section210B, Section104Pool, Holding1982, Holding1965.
    matchedLot: new RealisedGainLossMatchedLot(...),  // optional
    marketValue1965: new CurrencyAndAmount(...),  // optional
    reversed: true,  // optional
    taxTreatment: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RealisedGainLossChargeableGains>(json);
```


## Related Models

- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [RealisedGainLossMatchedLot](RealisedGainLossMatchedLot.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

