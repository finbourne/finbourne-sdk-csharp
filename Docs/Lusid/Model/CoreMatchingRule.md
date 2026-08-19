# Finbourne.Sdk.Lusid.Model.CoreMatchingRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleName** | **string** | Required | The reference name of the rule. |
| **LeftFormula** | **string** | Required | Derivation formula evaluated against the left side of the reconciliation. |
| **RightFormula** | **string** | Required | Derivation formula evaluated against the right side of the reconciliation. |
| **IsCaseSensitive** | **bool** | Optional | Whether the core rule comparison is case sensitive. Defaults to false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CoreMatchingRule(
    ruleName: "...",  // required — The reference name of the rule.
    leftFormula: "...",  // required — Derivation formula evaluated against the left side of the reconciliation.
    rightFormula: "...",  // required — Derivation formula evaluated against the right side of the reconciliation.
    isCaseSensitive: true  // optional — Whether the core rule comparison is case sensitive. Defaults to false.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CoreMatchingRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

