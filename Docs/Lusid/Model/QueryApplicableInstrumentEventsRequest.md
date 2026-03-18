# Finbourne.Sdk.Lusid.Model.QueryApplicableInstrumentEventsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WindowStart** | **DateTimeOffset** | Required | The start date of the window. |
| **WindowEnd** | **DateTimeOffset** | Required | The end date of the window. |
| **EffectiveAt** | **DateTimeOffset** | Required | The Effective date that splits query window into two parts: factual period and forecast period |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The set of portfolios and portfolio groups to which the instrument events must belong. |
| **ForecastingRecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryApplicableInstrumentEventsRequest(
    windowStart: DateTimeOffset.Now,  // required — The start date of the window.
    windowEnd: DateTimeOffset.Now,  // required — The end date of the window.
    effectiveAt: DateTimeOffset.Now,  // required — The Effective date that splits query window into two parts: factual period and forecast period
    portfolioEntityIds: new List<PortfolioEntityId>(),  // required — The set of portfolios and portfolio groups to which the instrument events must belong.
    forecastingRecipeId: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryApplicableInstrumentEventsRequest>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

