# Finbourne.Sdk.Lusid.Model.RecResultRelationalDataItem

A relational data point item within a rec result: one row of a relational dataset. The dataset and the unique  id of the data point identify the row. All rec types use this item shape. Also holds the display name of the  dataset.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RelationalDatasetDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RelationalDatasetDefinitionDisplayName** | **string** | Optional | The display name of the relational dataset definition the item&#39;s row belongs to, as it stood at the asAt the run read its data. Null where the run did not read it. |
| **RelationalDataPointUniqueId** | **string** | Required | The unique id of the relational data point the run read, as minted by the relational dataset store. Opaque: compare it whole, do not parse it. |
| **ItemType** | **string** | Required | The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. |
| **WritebackSuggestions** | [List&lt;WritebackSuggestion&gt;](WritebackSuggestion.md) | Required | The writebacks suggested against this item, as configured by the matching ruleset&#39;s writebackConfigurations. Only ever populated on target-side items. Suggestions only: a user is expected to review them before acting. Required, but may be empty. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultRelationalDataItem(
    relationalDatasetDefinitionId: new ResourceId(...),  // required
    relationalDatasetDefinitionDisplayName: "...",  // optional — The display name of the relational dataset definition the item&#39;s row belongs to, as it stood at the asAt the run read its data. Null where the run did not read it.
    relationalDataPointUniqueId: "...",  // required — The unique id of the relational data point the run read, as minted by the relational dataset store. Opaque: compare it whole, do not parse it.
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
var instance = JsonConvert.DeserializeObject<RecResultRelationalDataItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [WritebackSuggestion](WritebackSuggestion.md) — used in `WritebackSuggestions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

