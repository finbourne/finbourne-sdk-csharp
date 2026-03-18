# Finbourne.Sdk.Lusid.Model.QueryInstrumentEventsRequest

Instrument event query.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The time of the system at which to query for bucketed cashflows. |
| **WindowStart** | **DateTimeOffset** | Required | The start date of the window. |
| **WindowEnd** | **DateTimeOffset** | Required | The end date of the window. |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The set of portfolios and portfolio groups to which the instrument events must belong. |
| **EffectiveAt** | **DateTimeOffset** | Required | The Effective date used in the valuation of the cashflows. |
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **FilterInstrumentEvents** | **string** | Optional | Expression to filter the result set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryInstrumentEventsRequest(
    asAt: DateTimeOffset.Now,  // optional — The time of the system at which to query for bucketed cashflows.
    windowStart: DateTimeOffset.Now,  // required — The start date of the window.
    windowEnd: DateTimeOffset.Now,  // required — The end date of the window.
    portfolioEntityIds: new List<PortfolioEntityId>(),  // required — The set of portfolios and portfolio groups to which the instrument events must belong.
    effectiveAt: DateTimeOffset.Now,  // required — The Effective date used in the valuation of the cashflows.
    recipeId: new ResourceId(...),  // required
    filterInstrumentEvents: "..."  // optional — Expression to filter the result set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryInstrumentEventsRequest>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

