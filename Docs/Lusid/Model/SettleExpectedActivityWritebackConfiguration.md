# Finbourne.Sdk.Lusid.Model.SettleExpectedActivityWritebackConfiguration

Suggests settlement instructions where settlement on the origin side confirms expected settlement activity  on the target side. Only valid on a ruleset whose recType is SettlementActivity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MandatoryRuleNames** | [SettleExpectedActivityRuleNames](SettleExpectedActivityRuleNames.md) | Required | *No description available.* |
| **ResultPatterns** | [List&lt;WritebackResultPattern&gt;](WritebackResultPattern.md) | Required | The combinations of units difference and result cardinality for which writeback is suggested. A combination that is not present never produces a suggestion. Each combination may appear once, and the collection is returned in a canonical order regardless of the order supplied. |
| **WritebackType** | **string** | Required | Polymorphic discriminator, naming the change the writeback makes to LUSID. Supported types: SettleExpectedActivity, which is only valid when recType is SettlementActivity. Available values: SettleExpectedActivity. |
| **TargetSide** | **string** | Required | The side the writeback changes, the other being the source of truth. As the writeback changes LUSID, this side must draw on a native LUSID dataset rather than relational data. Available values: Left, Right. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettleExpectedActivityWritebackConfiguration(
    mandatoryRuleNames: new SettleExpectedActivityRuleNames(...),  // required
    resultPatterns: new List<WritebackResultPattern>(),  // required — The combinations of units difference and result cardinality for which writeback is suggested. A combination that is not present never produces a suggestion. Each combination may appear once, and the collection is returned in a canonical order regardless of the order supplied.
    writebackType: "...",  // required — Polymorphic discriminator, naming the change the writeback makes to LUSID. Supported types: SettleExpectedActivity, which is only valid when recType is SettlementActivity. Available values: SettleExpectedActivity.
    targetSide: "..."  // required — The side the writeback changes, the other being the source of truth. As the writeback changes LUSID, this side must draw on a native LUSID dataset rather than relational data. Available values: Left, Right.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettleExpectedActivityWritebackConfiguration>(json);
```


## Related Models

- [SettleExpectedActivityRuleNames](SettleExpectedActivityRuleNames.md)
- [WritebackResultPattern](WritebackResultPattern.md) — used in `ResultPatterns`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

