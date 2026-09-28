# Finbourne.Sdk.Lusid.Model.RecResultSettlementActivityItem

A settlement-activity item within a rec result.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ActivityId** | **string** | Optional | The settlement activity identifier. |
| **TransactionId** | **string** | Optional | The transaction identifier. |
| **SettlementInstructionId** | **string** | Optional | The settlement instruction identifier. |
| **HoldingImpacts** | [List&lt;RecResultHoldingImpact&gt;](RecResultHoldingImpact.md) | Required | The holdings, and where the source states them the tax lots, the item impacted. A distinct set ordered by holdingId then taxLotId; may be empty. An input transaction has not run the movements engine and impacts nothing yet. |
| **ItemType** | **string** | Required | The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction or SettlementActivity. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, and both transaction rec types produce Transaction items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultSettlementActivityItem(
    portfolioId: new ResourceId(...),  // required
    activityId: "...",  // optional — The settlement activity identifier.
    transactionId: "...",  // optional — The transaction identifier.
    settlementInstructionId: "...",  // optional — The settlement instruction identifier.
    holdingImpacts: new List<RecResultHoldingImpact>(),  // required — The holdings, and where the source states them the tax lots, the item impacted. A distinct set ordered by holdingId then taxLotId; may be empty. An input transaction has not run the movements engine and impacts nothing yet.
    itemType: "...",  // required — The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction or SettlementActivity. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, and both transaction rec types produce Transaction items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding.
    ruleAndAttributeValues:   // optional — The core rule, aggregate rule and supplemental attribute values for the item, keyed by name.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultSettlementActivityItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [RecResultHoldingImpact](RecResultHoldingImpact.md) — used in `HoldingImpacts`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

