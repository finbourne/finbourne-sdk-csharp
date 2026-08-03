# Finbourne.Sdk.Lusid.Model.ScenarioPreviewRequest

Request to preview a scenario against a portfolio's market data without running a valuation: the  portfolio's market data dependencies are resolved and the scenario's shifts applied, and the  response reports which targets each shift changed (with values before and after) and which market  data was skipped. Supply either a reference to a stored scenario or inline shift definitions  (for previewing a definition before saving it), not both.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The portfolios whose market data dependencies the scenario is previewed against. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date to resolve market data at. |
| **AsAt** | **DateTimeOffset?** | Optional | The as-at time to resolve at. Defaults to the latest. |
| **Scenario** | [ScenarioReference](ScenarioReference.md) | Optional | *No description available.* |
| **Shifts** | [List&lt;ScenarioShiftDefinition&gt;](ScenarioShiftDefinition.md) | Optional | Inline shift definitions to preview without saving a scenario, e.g. to test what a definition  would match while authoring it. Mutually exclusive with supplying a stored scenario reference. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioPreviewRequest(
    recipeId: new ResourceId(...),  // required
    portfolioEntityIds: new List<PortfolioEntityId>(),  // required — The portfolios whose market data dependencies the scenario is previewed against.
    effectiveAt: DateTimeOffset.Now,  // required — The effective date to resolve market data at.
    asAt: DateTimeOffset.Now,  // optional — The as-at time to resolve at. Defaults to the latest.
    scenario: new ScenarioReference(...),  // optional
    shifts: new List<ScenarioShiftDefinition>()  // optional — Inline shift definitions to preview without saving a scenario, e.g. to test what a definition  would match while authoring it. Mutually exclusive with supplying a stored scenario reference.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioPreviewRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [ScenarioReference](ScenarioReference.md)
- [ScenarioShiftDefinition](ScenarioShiftDefinition.md) — used in `Shifts`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

