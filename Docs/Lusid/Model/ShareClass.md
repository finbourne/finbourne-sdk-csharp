# Finbourne.Sdk.Lusid.Model.ShareClass

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The unique code for the Share Class. Must be unique within the Fund. |
| **Name** | **string** | Required | The display name of the Share Class. |
| **Description** | **string** | Optional | An optional description for the Share Class. |
| **ShareClassShortCode** | **string** | Required | A short code that uniquely identifies the share class within the Fund. |
| **LaunchPrice** | **decimal?** | Optional | The launch price set when a shareclass is added to the fund. Defaults to 1. |
| **LaunchDate** | **DateTimeOffset?** | Optional | The launch date set when a shareclass is added to the fund. Defaults to Fund Inception Date. |
| **ApportionmentFactor** | **decimal?** | Optional | The weighting factor used for apportionment across this share class. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | An optional set of properties to attach to the auto-created Instrument. Only applied when createInstrument is true. |
| **FundShareClassType** | **string** | Required | The Type of Share Class. Supported values are: Unitised / Non-Unitised / Series / Private Equity / Partnership. |
| **DistributionType** | **string** | Required | The type of distribution the ShareClass will calculate. Supported values are: Income, Accumulation. |
| **DomCcy** | **string** | Required | The domestic currency of the ShareClass instrument. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **UnitsPrecision** | **int?** | Optional | Decimal places for the share class units. |
| **PricePrecision** | **int?** | Optional | Decimal places for the share class price. |
| **RoundingConventions** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding conventions used for the ShareClass quotes. |
| **RoundingConventionsUnits** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding conventions used for the ShareClass units. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **DistributionPaymentType** | **string** | Optional | The tax treatment applied to distributions. Supported values are: Gross, Net. |
| **Hedging** | **string** | Required | Indicates whether the ShareClass applies currency hedging. Supported values are: Invalid, None, ApplyHedging. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClass(
    code: "...",  // required — The unique code for the Share Class. Must be unique within the Fund.
    name: "...",  // required — The display name of the Share Class.
    description: "...",  // optional — An optional description for the Share Class.
    shareClassShortCode: "...",  // required — A short code that uniquely identifies the share class within the Fund.
    launchPrice: 0.0d,  // optional — The launch price set when a shareclass is added to the fund. Defaults to 1.
    launchDate: DateTimeOffset.Now,  // optional — The launch date set when a shareclass is added to the fund. Defaults to Fund Inception Date.
    apportionmentFactor: 0.0d,  // optional — The weighting factor used for apportionment across this share class.
    properties: new Property(...),  // optional — An optional set of properties to attach to the auto-created Instrument. Only applied when createInstrument is true.
    fundShareClassType: "...",  // required — The Type of Share Class. Supported values are: Unitised / Non-Unitised / Series / Private Equity / Partnership.
    distributionType: "...",  // required — The type of distribution the ShareClass will calculate. Supported values are: Income, Accumulation.
    domCcy: "...",  // required — The domestic currency of the ShareClass instrument.
    tradingConventions: new TradingConventions(...),  // optional
    unitsPrecision: 0,  // optional — Decimal places for the share class units.
    pricePrecision: 0,  // optional — Decimal places for the share class price.
    roundingConventions: new List<SimpleRoundingConvention>(),  // optional — Rounding conventions used for the ShareClass quotes.
    roundingConventionsUnits: new List<SimpleRoundingConvention>(),  // optional — Rounding conventions used for the ShareClass units.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    distributionPaymentType: "...",  // optional — The tax treatment applied to distributions. Supported values are: Gross, Net.
    hedging: "..."  // required — Indicates whether the ShareClass applies currency hedging. Supported values are: Invalid, None, ApplyHedging.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ShareClass>(json);
```

- [Property](Property.md) — used in `Properties`
- [TradingConventions](TradingConventions.md)
- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventions`
- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventionsUnits`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

