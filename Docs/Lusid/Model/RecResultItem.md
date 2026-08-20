# Finbourne.Sdk.Lusid.Model.RecResultItem

An individual item that makes up (one side of) a rec result. Polymorphic by rec type / item type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ItemType** | **string** | Required | The polymorphic item-type discriminator (e.g. SettlementActivity, Holding, Transaction). Available values: SettlementActivity, Holding, Transaction. |
| **RuleAndAttributeValues** | **Dictionary&lt;string, string&gt;** | Optional | The core rule, aggregate rule and supplemental attribute values for the item, keyed by name. *(read-only)* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultItem(
    itemType: "...",  // required — The polymorphic item-type discriminator (e.g. SettlementActivity, Holding, Transaction). Available values: SettlementActivity, Holding, Transaction.
    ruleAndAttributeValues:   // optional — The core rule, aggregate rule and supplemental attribute values for the item, keyed by name.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

