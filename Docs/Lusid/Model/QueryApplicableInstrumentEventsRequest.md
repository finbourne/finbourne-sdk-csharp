# Finbourne.Sdk.Lusid.Model.QueryApplicableInstrumentEventsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WindowStart** | **DateTimeOffset** | Required | The start date of the window. |
| **WindowEnd** | **DateTimeOffset** | Required | The end date of the window. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The Effective date that splits query window into two parts: factual period and forecast period. Optional - a timeline (with an optional closed period) may be supplied instead to derive the effective date. |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The set of portfolios and portfolio groups to which the instrument events must belong. |
| **ForecastingRecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TimelineScope** | **string** | Optional | The scope of the timeline to be used when building the instrument events. |
| **TimelineCode** | **string** | Optional | The code of the timeline to be used when building the instrument events. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods. |
| **ClosedPeriodId** | **string** | Optional | The id of the closed period, on the given timeline, to be used when building the instrument events. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryApplicableInstrumentEventsRequest(
    windowStart: DateTimeOffset.Now,  // required — The start date of the window.
    windowEnd: DateTimeOffset.Now,  // required — The end date of the window.
    effectiveAt: DateTimeOffset.Now,  // optional — The Effective date that splits query window into two parts: factual period and forecast period. Optional - a timeline (with an optional closed period) may be supplied instead to derive the effective date.
    portfolioEntityIds: new List<PortfolioEntityId>(),  // required — The set of portfolios and portfolio groups to which the instrument events must belong.
    forecastingRecipeId: new ResourceId(...),  // required
    timelineScope: "...",  // optional — The scope of the timeline to be used when building the instrument events.
    timelineCode: "...",  // optional — The code of the timeline to be used when building the instrument events. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods.
    closedPeriodId: "..."  // optional — The id of the closed period, on the given timeline, to be used when building the instrument events.
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

