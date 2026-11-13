# Finbourne.Sdk.Lusid.Model.RecResultCustomEntityItem

An item within a rec result for one custom entity: one entity on a side of a LusidEntity rec of a custom entity  type. The entity unique id identifies it. The item also holds the display name and the identifiers of the entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The custom entity type of the entity the run read. It starts with a tilde. |
| **EntityUniqueId** | **string** | Required | The unique id of the entity the run read. It identifies the entity across scopes. |
| **EntityDisplayName** | **string** | Optional | The display name of the entity, as it stood at the dates the run read its side. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | The unique identifiers of the entity, keyed by identifier property key. The values are as at the dates the run read the side of the item, so they can differ from the current values. |
| **ItemType** | **string** | Required | The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio, CustomEntity. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. |
| **WritebackSuggestions** | [List&lt;WritebackSuggestion&gt;](WritebackSuggestion.md) | Required | The writebacks suggested against this item, as configured by the matching ruleset&#39;s writebackConfigurations. Only ever populated on target-side items. Suggestions only: a user is expected to review them before acting. Required, but may be empty. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultCustomEntityItem(
    entityType: "...",  // required — The custom entity type of the entity the run read. It starts with a tilde.
    entityUniqueId: "...",  // required — The unique id of the entity the run read. It identifies the entity across scopes.
    entityDisplayName: "...",  // optional — The display name of the entity, as it stood at the dates the run read its side.
    identifiers: ,  // required — The unique identifiers of the entity, keyed by identifier property key. The values are as at the dates the run read the side of the item, so they can differ from the current values.
    itemType: "...",  // required — The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio, CustomEntity.
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
var instance = JsonConvert.DeserializeObject<RecResultCustomEntityItem>(json);
```

- [WritebackSuggestion](WritebackSuggestion.md) — used in `WritebackSuggestions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

