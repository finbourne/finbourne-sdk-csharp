# Finbourne.Sdk.Lusid.Model.TaxDeemedDisposalResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The deterministic identifier of the deemed disposal, derived from the holding and date. |
| **HoldingId** | **string** | Optional | The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier. |
| **InstrumentId** | **string** | Optional | The LUSID unique identifier of the instrument. |
| **InstrumentName** | **string** | Optional | The name of the instrument. |
| **PortfolioCode** | **string** | Optional | The code of the portfolio the holding sits in, or the pooled marker for a company. |
| **Date** | **DateTimeOffset** | Optional | The date the deemed disposal arises, the end of the period. |
| **Units** | **decimal** | Optional | The units disposed of. |
| **Cost** | **decimal** | Optional | The allowable cost of the units disposed of. |
| **MarketValue** | **decimal** | Optional | The market value of the holding at the deemed-disposal date. |
| **NetAmount** | **decimal** | Optional | The net deemed amount, gains less losses. |
| **Notional** | **bool** | Optional | True when the deemed disposal is notional, as it is for a member fund, rather than an actual deemed disposal at company level. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxDeemedDisposalResponse(
    id: "...",  // optional — The deterministic identifier of the deemed disposal, derived from the holding and date.
    holdingId: "...",  // optional — The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier.
    instrumentId: "...",  // optional — The LUSID unique identifier of the instrument.
    instrumentName: "...",  // optional — The name of the instrument.
    portfolioCode: "...",  // optional — The code of the portfolio the holding sits in, or the pooled marker for a company.
    date: DateTimeOffset.Now,  // optional — The date the deemed disposal arises, the end of the period.
    units: 0.0d,  // optional — The units disposed of.
    cost: 0.0d,  // optional — The allowable cost of the units disposed of.
    marketValue: 0.0d,  // optional — The market value of the holding at the deemed-disposal date.
    netAmount: 0.0d,  // optional — The net deemed amount, gains less losses.
    notional: true  // optional — True when the deemed disposal is notional, as it is for a member fund, rather than an actual deemed disposal at company level.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxDeemedDisposalResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

