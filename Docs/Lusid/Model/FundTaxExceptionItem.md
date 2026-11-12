# Finbourne.Sdk.Lusid.Model.FundTaxExceptionItem

A tax exception row seen across funds, so the fund and the owning life-company entity travel with it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarClient** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Fund** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Id** | **string** | Required | An identifier stable within a response, built from the category, portfolio and instrument. |
| **Category** | **string** | Required | The kind of exception: UnmatchedDisposal, NegativePool, MissingValuation or UnclassifiedInstrument. |
| **Severity** | **string** | Required | Error when the exception blocks the tax computation, Warning when it casts doubt on it. |
| **Portfolio** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Instrument** | **string** | Optional | The LUSID unique identifier of the instrument the exception was raised against. |
| **Message** | **string** | Required | A description of the exception. |
| **RaisedAt** | **DateTimeOffset** | Required | The asAt the exception was observed at. |
| **TaxAtStake** | **decimal?** | Optional | The tax effect, in the Fund&#39;s base currency, of the position or gain the exception blocks, at the Fund&#39;s configured rate. Absent when the rate or the exposure is not known. |
| **RootCause** | [TaxExceptionRootCause](TaxExceptionRootCause.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundTaxExceptionItem(
    varClient: new ResourceId(...),  // optional
    fund: new ResourceId(...),  // required
    id: "...",  // required — An identifier stable within a response, built from the category, portfolio and instrument.
    category: "...",  // required — The kind of exception: UnmatchedDisposal, NegativePool, MissingValuation or UnclassifiedInstrument.
    severity: "...",  // required — Error when the exception blocks the tax computation, Warning when it casts doubt on it.
    portfolio: new ResourceId(...),  // required
    instrument: "...",  // optional — The LUSID unique identifier of the instrument the exception was raised against.
    message: "...",  // required — A description of the exception.
    raisedAt: DateTimeOffset.Now,  // required — The asAt the exception was observed at.
    taxAtStake: 0.0d,  // optional — The tax effect, in the Fund&#39;s base currency, of the position or gain the exception blocks, at the Fund&#39;s configured rate. Absent when the rate or the exposure is not known.
    rootCause: new TaxExceptionRootCause(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundTaxExceptionItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [TaxExceptionRootCause](TaxExceptionRootCause.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

