# Finbourne.Sdk.Lusid.Model.RecResultTransactionItem

A transaction item within a rec result. Names the portfolio and the transaction's resolved instrument alongside,  for display.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioDisplayName** | **string** | Optional | The display name of the item&#39;s portfolio, as it stood at the asAt the run read its data. Null where the run did not read it. |
| **TransactionId** | **string** | Optional | The transaction identifier. |
| **TransactionInstrumentScope** | **string** | Optional | The scope of the transaction&#39;s resolved instrument. Null where the source does not state one. |
| **TransactionLusidInstrumentId** | **string** | Optional | The LUID of the transaction&#39;s resolved instrument. Null where the source does not state it. |
| **TransactionInstrumentName** | **string** | Optional | The name of the transaction&#39;s resolved instrument, as it stood at the asAt the run read its data. Null where the run did not resolve it. |
| **HoldingImpacts** | [List&lt;RecResultHoldingImpact&gt;](RecResultHoldingImpact.md) | Required | The holdings, and where the source states them the tax lots, the item impacted. A distinct set ordered by holdingId then taxLotId; may be empty. An input transaction has not run the movements engine and impacts nothing yet. |
| **ItemType** | **string** | Required | The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. |
| **WritebackSuggestions** | [List&lt;WritebackSuggestion&gt;](WritebackSuggestion.md) | Required | The writebacks suggested against this item, as configured by the matching ruleset&#39;s writebackConfigurations. Only ever populated on target-side items. Suggestions only: a user is expected to review them before acting. Required, but may be empty. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultTransactionItem(
    portfolioId: new ResourceId(...),  // required
    portfolioDisplayName: "...",  // optional — The display name of the item&#39;s portfolio, as it stood at the asAt the run read its data. Null where the run did not read it.
    transactionId: "...",  // optional — The transaction identifier.
    transactionInstrumentScope: "...",  // optional — The scope of the transaction&#39;s resolved instrument. Null where the source does not state one.
    transactionLusidInstrumentId: "...",  // optional — The LUID of the transaction&#39;s resolved instrument. Null where the source does not state it.
    transactionInstrumentName: "...",  // optional — The name of the transaction&#39;s resolved instrument, as it stood at the asAt the run read its data. Null where the run did not resolve it.
    holdingImpacts: new List<RecResultHoldingImpact>(),  // required — The holdings, and where the source states them the tax lots, the item impacted. A distinct set ordered by holdingId then taxLotId; may be empty. An input transaction has not run the movements engine and impacts nothing yet.
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
var instance = JsonConvert.DeserializeObject<RecResultTransactionItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [RecResultHoldingImpact](RecResultHoldingImpact.md) — used in `HoldingImpacts`
- [WritebackSuggestion](WritebackSuggestion.md) — used in `WritebackSuggestions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

