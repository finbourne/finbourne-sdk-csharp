# Finbourne.Sdk.Lusid.Model.RecResultResourceIdItem

An item within a rec result for one LUSID entity that a scope and a code identify: one entity on a side of a  LusidEntity rec. The itemType is the entity type. The entity unique id identifies it. The item also holds the  display name of the entity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EntityUniqueId** | **string** | Required | The unique id of the entity the run read. It identifies the entity across scopes. |
| **EntityDisplayName** | **string** | Optional | The display name of the entity, as it stood at the dates the run read its side. |
| **ItemType** | **string** | Required | The polymorphic item-type discriminator: Holding, ValuedHolding, Transaction, SettlementActivity, RelationalDataPoint or the entity type of a LusidEntity rec. Names the item rather than the rec type: Holding and CashHolding recs produce Holding items, a Valuation rec produces ValuedHolding items, both transaction rec types produce Transaction items, and a relational dataset side produces RelationalDataPoint items whatever the rec type. A LusidEntity rec produces items of its entity type, for example Instrument items. Available values: SettlementActivity, Holding, Transaction, ValuedHolding, RelationalDataPoint, Instrument, LegalEntity, Portfolio. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. |
| **WritebackSuggestions** | [List&lt;WritebackSuggestion&gt;](WritebackSuggestion.md) | Required | The writebacks suggested against this item, as configured by the matching ruleset&#39;s writebackConfigurations. Only ever populated on target-side items. Suggestions only: a user is expected to review them before acting. Required, but may be empty. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultResourceIdItem(
    id: new ResourceId(...),  // required
    entityUniqueId: "...",  // required — The unique id of the entity the run read. It identifies the entity across scopes.
    entityDisplayName: "...",  // optional — The display name of the entity, as it stood at the dates the run read its side.
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
var instance = JsonConvert.DeserializeObject<RecResultResourceIdItem>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [WritebackSuggestion](WritebackSuggestion.md) — used in `WritebackSuggestions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

