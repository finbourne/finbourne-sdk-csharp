# Finbourne.Sdk.Lusid.Model.WithholdingTaxMatchedRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MatchedRuleId** | **string** | Required | The identifier booking stamps for the matched row: its series identifiers and effective date. |
| **MatchedDataset** | **string** | Required | The dataset the matched row came from: Main or Anomaly. |
| **RuleSource** | **string** | Optional | The rule source of the matched row. Null when the row has none. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date of the matched row version. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxMatchedRule(
    matchedRuleId: "...",  // required — The identifier booking stamps for the matched row: its series identifiers and effective date.
    matchedDataset: "...",  // required — The dataset the matched row came from: Main or Anomaly.
    ruleSource: "...",  // optional — The rule source of the matched row. Null when the row has none.
    effectiveAt: DateTimeOffset.Now  // required — The effective date of the matched row version.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxMatchedRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

