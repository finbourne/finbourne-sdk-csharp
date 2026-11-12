# Finbourne.Sdk.Lusid.Model.MarginRunRequest

A request to value collateral agreements for a business date and publish their margin calls.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The business date, datetime or cut label to value the agreements at. With an effectiveFrom, the last date of the span. |
| **AsAt** | **DateTimeOffset?** | Optional | The asAt datetime to read agreements, portfolios and market data at. Defaults to the current LUSID system datetime if not specified. |
| **AgreementFilter** | **string** | Optional | An expression selecting the collateral agreements to run, in the same syntax as listing collateral agreements. Every agreement the caller may calculate margin for is run if not specified. |
| **Scenarios** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The stored scenarios to value the agreements under, each as a what-if beside the base market, which the run always values. A scenario&#39;s calls are served beside the base calls only when asked for, and cannot be accepted, disputed or matched to a counterparty demand. At most 20. Only the base market is valued if not specified. |
| **EffectiveFrom** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The first business date, datetime or cut label of a span ending at effectiveAt. Each weekday from it to effectiveAt is valued as a run of its own, all at the same asAt, and a date after the asAt is a projection valued on the market as at the asAt that cannot be accepted, disputed or matched to a counterparty demand. At most 130 weekdays. Only effectiveAt is valued if not specified. |
| **CaptureDiagnostics** | **bool?** | Optional | Whether to store the working behind the run&#39;s figures so that it can be explained. Specified, it is honoured. Not specified, the working is stored only for a run of a single date with no scenarios, since storing it costs time and space that a span or what-if run is not expected to repay. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRunRequest(
    effectiveAt: new DateTimeOrCutLabel(...),  // required — The business date, datetime or cut label to value the agreements at. With an effectiveFrom, the last date of the span.
    asAt: DateTimeOffset.Now,  // optional — The asAt datetime to read agreements, portfolios and market data at. Defaults to the current LUSID system datetime if not specified.
    agreementFilter: "...",  // optional — An expression selecting the collateral agreements to run, in the same syntax as listing collateral agreements. Every agreement the caller may calculate margin for is run if not specified.
    scenarios: new List<ResourceId>(),  // optional — The stored scenarios to value the agreements under, each as a what-if beside the base market, which the run always values. A scenario&#39;s calls are served beside the base calls only when asked for, and cannot be accepted, disputed or matched to a counterparty demand. At most 20. Only the base market is valued if not specified.
    effectiveFrom: new DateTimeOrCutLabel(...),  // optional — The first business date, datetime or cut label of a span ending at effectiveAt. Each weekday from it to effectiveAt is valued as a run of its own, all at the same asAt, and a date after the asAt is a projection valued on the market as at the asAt that cannot be accepted, disputed or matched to a counterparty demand. At most 130 weekdays. Only effectiveAt is valued if not specified.
    captureDiagnostics: true  // optional — Whether to store the working behind the run&#39;s figures so that it can be explained. Specified, it is honoured. Not specified, the working is stored only for a run of a single date with no scenarios, since storing it costs time and space that a span or what-if run is not expected to repay.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarginRunRequest>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`
- [ResourceId](ResourceId.md) — used in `Scenarios`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveFrom`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

