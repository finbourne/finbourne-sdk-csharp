# Finbourne.Sdk.Lusid.Model.UpsertReferencePortfolioConstituentsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveFrom** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The first date from which the weights will apply |
| **WeightType** | **string** | Required | Available values: Static, Floating, Periodical. |
| **PeriodType** | **string** | Optional | Available values: Daily, Weekly, Monthly, Quarterly, Annually. |
| **PeriodCount** | **int?** | Optional | *No description available.* |
| **Constituents** | [List&lt;ReferencePortfolioConstituentRequest&gt;](ReferencePortfolioConstituentRequest.md) | Required | Set of constituents (instrument/weight pairings) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertReferencePortfolioConstituentsRequest(
    effectiveFrom: new DateTimeOrCutLabel(...),  // required — The first date from which the weights will apply
    weightType: "...",  // required — Available values: Static, Floating, Periodical.
    periodType: "...",  // optional — Available values: Daily, Weekly, Monthly, Quarterly, Annually.
    periodCount: 0,  // optional
    constituents: new List<ReferencePortfolioConstituentRequest>()  // required — Set of constituents (instrument/weight pairings)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertReferencePortfolioConstituentsRequest>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveFrom`
- [ReferencePortfolioConstituentRequest](ReferencePortfolioConstituentRequest.md) — used in `Constituents`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

