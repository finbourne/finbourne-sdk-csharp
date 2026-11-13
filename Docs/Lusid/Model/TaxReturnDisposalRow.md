# Finbourne.Sdk.Lusid.Model.TaxReturnDisposalRow

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingId** | **string** | Optional | The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier. |
| **InstrumentId** | **string** | Optional | The LUSID unique identifier of the instrument. |
| **InstrumentName** | **string** | Optional | The name of the instrument. |
| **PortfolioCode** | **string** | Optional | The code of the portfolio the holding sits in, or the pooled marker for a company. |
| **DisposalDate** | **DateTimeOffset** | Optional | The date of the disposal. |
| **Units** | **decimal** | Optional | The units disposed of. |
| **Cost** | **decimal** | Optional | The allowable cost of the units disposed of. |
| **IndexationAllowanceTaken** | **decimal** | Optional | The indexation allowance deducted when arriving at the chargeable gain. |
| **ChargeableGain** | **decimal** | Optional | The chargeable gain or allowable loss on the disposal, negative for a loss. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnDisposalRow(
    holdingId: "...",  // optional — The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier.
    instrumentId: "...",  // optional — The LUSID unique identifier of the instrument.
    instrumentName: "...",  // optional — The name of the instrument.
    portfolioCode: "...",  // optional — The code of the portfolio the holding sits in, or the pooled marker for a company.
    disposalDate: DateTimeOffset.Now,  // optional — The date of the disposal.
    units: 0.0d,  // optional — The units disposed of.
    cost: 0.0d,  // optional — The allowable cost of the units disposed of.
    indexationAllowanceTaken: 0.0d,  // optional — The indexation allowance deducted when arriving at the chargeable gain.
    chargeableGain: 0.0d  // optional — The chargeable gain or allowable loss on the disposal, negative for a loss.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnDisposalRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

