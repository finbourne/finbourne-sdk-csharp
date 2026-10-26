# Finbourne.Sdk.Lusid.Model.MarginRunRequest

A request to value collateral agreements for a business date and publish their margin calls.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The business date, datetime or cut label to value the agreements at. |
| **AsAt** | **DateTimeOffset?** | Optional | The asAt datetime to read agreements, portfolios and market data at. Defaults to the current LUSID system datetime if not specified. |
| **AgreementFilter** | **string** | Optional | An expression selecting the collateral agreements to run, in the same syntax as listing collateral agreements. Every agreement the caller may calculate margin for is run if not specified. |
| **Scenario** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarginRunRequest(
    effectiveAt: new DateTimeOrCutLabel(...),  // required — The business date, datetime or cut label to value the agreements at.
    asAt: DateTimeOffset.Now,  // optional — The asAt datetime to read agreements, portfolios and market data at. Defaults to the current LUSID system datetime if not specified.
    agreementFilter: "...",  // optional — An expression selecting the collateral agreements to run, in the same syntax as listing collateral agreements. Every agreement the caller may calculate margin for is run if not specified.
    scenario: new ResourceId(...)  // optional
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
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

