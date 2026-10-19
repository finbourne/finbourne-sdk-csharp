# Finbourne.Sdk.Lusid.Model.ShareClass

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | Unique instrument identifiers |
| **Series** | [List&lt;Series&gt;](Series.md) | Optional | The series that belong to this Share Class - only relevant if InvestorType is Series. |
| **Name** | **string** | Required | The display name of the Share Class. |
| **Description** | **string** | Optional | An optional description for the Share Class. |
| **ShareClassShortCode** | **string** | Required | A short code that uniquely identifies the share class within the Fund. |
| **LaunchPrice** | **decimal?** | Optional | The launch price set when a shareclass is added to the fund. Defaults to 1. |
| **LaunchDate** | **DateTimeOffset?** | Optional | The launch date set when a shareclass is added to the fund. Defaults to Fund Inception Date. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | An optional set of properties for the Share Class. These must be from the &#39;Instrument&#39; domain. |
| **InvestorType** | **string** | Required | The Type of Share Class. Available values: Unitised. |
| **DistributionType** | **string** | Optional | The type of distribution the ShareClass will calculate. Available values: Income, Accumulation. |
| **DomCcy** | **string** | Required | The domestic currency of the ShareClass instrument. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **RoundingConventionsPrice** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding conventions used for the ShareClass quotes. |
| **RoundingConventionsUnits** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding conventions used for the ShareClass units. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **DistributionPaymentType** | **string** | Optional | The tax treatment applied to distributions. Available values: Invalid, Gross, Net. |
| **Hedging** | **string** | Optional | Indicates whether the ShareClass applies currency hedging. Available values: Invalid, None, ApplyHedging. |
| **WhtParameters** | [WhtParameters](WhtParameters.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ShareClass(
    instrumentIdentifiers: ,  // optional — Unique instrument identifiers
    series: new List<Series>(),  // optional — The series that belong to this Share Class - only relevant if InvestorType is Series.
    name: "...",  // required — The display name of the Share Class.
    description: "...",  // optional — An optional description for the Share Class.
    shareClassShortCode: "...",  // required — A short code that uniquely identifies the share class within the Fund.
    launchPrice: 0.0d,  // optional — The launch price set when a shareclass is added to the fund. Defaults to 1.
    launchDate: DateTimeOffset.Now,  // optional — The launch date set when a shareclass is added to the fund. Defaults to Fund Inception Date.
    properties: new Property(...),  // optional — An optional set of properties for the Share Class. These must be from the &#39;Instrument&#39; domain.
    investorType: "...",  // required — The Type of Share Class. Available values: Unitised.
    distributionType: "...",  // optional — The type of distribution the ShareClass will calculate. Available values: Income, Accumulation.
    domCcy: "...",  // required — The domestic currency of the ShareClass instrument.
    tradingConventions: new TradingConventions(...),  // optional
    roundingConventionsPrice: new List<SimpleRoundingConvention>(),  // optional — Rounding conventions used for the ShareClass quotes.
    roundingConventionsUnits: new List<SimpleRoundingConvention>(),  // optional — Rounding conventions used for the ShareClass units.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    distributionPaymentType: "...",  // optional — The tax treatment applied to distributions. Available values: Invalid, Gross, Net.
    hedging: "...",  // optional — Indicates whether the ShareClass applies currency hedging. Available values: Invalid, None, ApplyHedging.
    whtParameters: new WhtParameters(...)  // optional
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

- [Series](Series.md) — used in `Series`
- [Property](Property.md) — used in `Properties`
- [TradingConventions](TradingConventions.md)
- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventionsPrice`
- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventionsUnits`
- [TimeZoneConventions](TimeZoneConventions.md)
- [WhtParameters](WhtParameters.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

