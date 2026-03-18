# Finbourne.Sdk.Lusid.Model.PostCloseActivity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The type of the entity, possible values are: * &#x60;PortfolioTransaction&#x60;, * &#x60;Instrument&#x60;, * &#x60;InstrumentEvent&#x60;, * &#x60;InstrumentEventInstruction&#x60;, * &#x60;PortfolioSettlementInstruction&#x60;, and, * &#x60;Quote&#x60;. |
| **EntityUniqueId** | **string** | Required | The entity unique ID. The expected format for each entity is: | entityType                       | entityUniqueId                                    | |- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -|- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --| | &#x60;PortfolioTransaction&#x60;           | &#x60;portfolioUniqueId_transactionId&#x60;                 | | &#x60;Instrument&#x60;                     | &#x60;instrumentUniqueId&#x60;                              | | &#x60;InstrumentEvent&#x60;                | &#x60;corporateActionSourceUniqueId_instrumentEventId&#x60; | | &#x60;InstrumentEventInstruction&#x60;     | &#x60;portfolioUniqueId_instructionId&#x60;                 | | &#x60;PortfolioSettlementInstruction&#x60; | &#x60;portfolioUniqueId_settlementInstructionId&#x60;       | | &#x60;Quote&#x60;                          | &#x60;quoteSeriesUniqueId_quoteSeriesInstrumentId&#x60;     | |
| **AsAt** | **DateTimeOffset** | Required | The &#x60;AsAt&#x60; time of the event that needs to be added to the closed period. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The &#x60;EffectiveAt&#x60; time of the event that need to be added to the closed period. This can be a date or cut label. Only applicable for &#x60;Quote&#x60; post-close activities. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostCloseActivity(
    entityType: "...",  // required — The type of the entity, possible values are: * &#x60;PortfolioTransaction&#x60;, * &#x60;Instrument&#x60;, * &#x60;InstrumentEvent&#x60;, * &#x60;InstrumentEventInstruction&#x60;, * &#x60;PortfolioSettlementInstruction&#x60;, and, * &#x60;Quote&#x60;.
    entityUniqueId: "...",  // required — The entity unique ID. The expected format for each entity is: | entityType                       | entityUniqueId                                    | |- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -|- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --| | &#x60;PortfolioTransaction&#x60;           | &#x60;portfolioUniqueId_transactionId&#x60;                 | | &#x60;Instrument&#x60;                     | &#x60;instrumentUniqueId&#x60;                              | | &#x60;InstrumentEvent&#x60;                | &#x60;corporateActionSourceUniqueId_instrumentEventId&#x60; | | &#x60;InstrumentEventInstruction&#x60;     | &#x60;portfolioUniqueId_instructionId&#x60;                 | | &#x60;PortfolioSettlementInstruction&#x60; | &#x60;portfolioUniqueId_settlementInstructionId&#x60;       | | &#x60;Quote&#x60;                          | &#x60;quoteSeriesUniqueId_quoteSeriesInstrumentId&#x60;     |
    asAt: DateTimeOffset.Now,  // required — The &#x60;AsAt&#x60; time of the event that needs to be added to the closed period.
    effectiveAt: new DateTimeOrCutLabel(...)  // optional — The &#x60;EffectiveAt&#x60; time of the event that need to be added to the closed period. This can be a date or cut label. Only applicable for &#x60;Quote&#x60; post-close activities.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostCloseActivity>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

