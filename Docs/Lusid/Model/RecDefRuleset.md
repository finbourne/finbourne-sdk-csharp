# Finbourne.Sdk.Lusid.Model.RecDefRuleset

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecType** | **string** | Required | The type of reconciliation this entry configures. Must be valid for the definitionType, and must match the reconciliationType of the referenced matching ruleset. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity. |
| **MatchingRulesetId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RelationalDataFilter** | **string** | Optional | Selects the slice of the relational dataset this definition draws from, e.g. \&quot;custodian eq &#39;NT&#39;\&quot;. Only permitted when the referenced ruleset declares a relational side, and combined with AND at run time with that ruleset&#39;s own filter for the side. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefRuleset(
    recType: "...",  // required — The type of reconciliation this entry configures. Must be valid for the definitionType, and must match the reconciliationType of the referenced matching ruleset. Available values: Holding, CashHolding, Valuation, InputTransaction, OutputTransaction, SettlementActivity.
    matchingRulesetId: new ResourceId(...),  // required
    relationalDataFilter: "..."  // optional — Selects the slice of the relational dataset this definition draws from, e.g. \&quot;custodian eq &#39;NT&#39;\&quot;. Only permitted when the referenced ruleset declares a relational side, and combined with AND at run time with that ruleset&#39;s own filter for the side.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefRuleset>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

