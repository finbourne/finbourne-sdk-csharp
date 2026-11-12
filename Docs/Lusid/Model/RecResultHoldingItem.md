# Finbourne.Sdk.Lusid.Model.RecResultHoldingItem

A holding-shaped item within a rec result: the holding a Holding or CashHolding rec reconciled  (itemType Holding), or the one a Valuation rec valued (itemType ValuedHolding). Also holds the display names  of the portfolio and the holding's instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioDisplayName** | **string** | Optional | The display name of the item&#39;s portfolio, as it stood at the asAt the run read its data. Null where the run did not read it. |
| **HoldingId** | **string** | Optional | The holding identifier, at holding level: the same id whichever granularity the holding was read at, so that items of different rec types over one holding name it alike. |
| **TaxLotId** | **string** | Optional | The tax lot the item is, where the source row was a single lot: a lot of a position read by tax lot, or a cash commitment. Null for an aggregated position and for a cash balance. Opaque: compare it whole, do not parse it. |
| **HoldingInstrumentScope** | **string** | Optional | The scope of the holding&#39;s instrument. Null where the source does not state one. |
| **HoldingLusidInstrumentId** | **string** | Optional | The LUID of the holding&#39;s instrument. Null where the source does not state it. |
| **HoldingInstrumentName** | **string** | Optional | The name of the holding&#39;s instrument, as it stood at the asAt the run read its data. Null where the run did not resolve it. |
| **ItemType** | **string** | Required | The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. |
| **WritebackSuggestions** | [List&lt;WritebackSuggestion&gt;](WritebackSuggestion.md) | Required | The writebacks suggested against this item, as configured by the matching ruleset&#39;s writebackConfigurations. Only ever populated on target-side items. Suggestions only: a user is expected to review them before acting. Required, but may be empty. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultHoldingItem(
    portfolioId: new ResourceId(...),  // required
    portfolioDisplayName: "...",  // optional — The display name of the item&#39;s portfolio, as it stood at the asAt the run read its data. Null where the run did not read it.
    holdingId: "...",  // optional — The holding identifier, at holding level: the same id whichever granularity the holding was read at, so that items of different rec types over one holding name it alike.
    taxLotId: "...",  // optional — The tax lot the item is, where the source row was a single lot: a lot of a position read by tax lot, or a cash commitment. Null for an aggregated position and for a cash balance. Opaque: compare it whole, do not parse it.
    holdingInstrumentScope: "...",  // optional — The scope of the holding&#39;s instrument. Null where the source does not state one.
    holdingLusidInstrumentId: "...",  // optional — The LUID of the holding&#39;s instrument. Null where the source does not state it.
    holdingInstrumentName: "...",  // optional — The name of the holding&#39;s instrument, as it stood at the asAt the run read its data. Null where the run did not resolve it.
    itemType: "...",  // required — The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio.
    ruleAndAttributeValues: ,  // optional — The core rule, aggregate rule and supplemental attribute values for the item, keyed by name.
    writebackSuggestions: new List<WritebackSuggestion>()  // required — The writebacks suggested against this item, as configured by the matching ruleset&#39;s writebackConfigurations. Only ever populated on target-side items. Suggestions only: a user is expected to review them before acting. Required, but may be empty.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultHoldingItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [WritebackSuggestion](WritebackSuggestion.md) — used in `WritebackSuggestions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

