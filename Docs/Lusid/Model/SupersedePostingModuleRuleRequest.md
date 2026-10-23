# Finbourne.Sdk.Lusid.Model.SupersedePostingModuleRuleRequest

The next version of a Posting Rule, which takes over from its latest version on an accounting date
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The identifier of the Posting Rule. At most one rule in the request may have the ruleId of the superseded rule. If it does, the existing rule is capped so that it stops applying from this rule&#39;s EffectiveFrom, and this rule is created as its next version. Otherwise this rule is created as a new rule. |
| **EffectiveFrom** | **DateTimeOffset** | Required | The inclusive accounting date from which this rule applies. If this rule has the ruleId of the superseded rule, the superseded rule&#39;s latest version stops applying from this date, unless it already ends by then; it is never extended. |
| **EffectiveUntil** | **DateTimeOffset?** | Optional | The exclusive accounting date until which this rule applies. If not set, it applies until the end of time. |
| **GeneralLedgerAccountCode** | **string** | Required | The general ledger account this rule posts the Activity credit or debit to. |
| **RuleFilter** | **string** | Required | The filter syntax for this rule. See https://support.lusid.com/docs/assigning-economic-activity-to-general-ledger-accounts-using-posting-rules for more information on filter syntax. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SupersedePostingModuleRuleRequest(
    ruleId: "...",  // required — The identifier of the Posting Rule. At most one rule in the request may have the ruleId of the superseded rule. If it does, the existing rule is capped so that it stops applying from this rule&#39;s EffectiveFrom, and this rule is created as its next version. Otherwise this rule is created as a new rule.
    effectiveFrom: DateTimeOffset.Now,  // required — The inclusive accounting date from which this rule applies. If this rule has the ruleId of the superseded rule, the superseded rule&#39;s latest version stops applying from this date, unless it already ends by then; it is never extended.
    effectiveUntil: DateTimeOffset.Now,  // optional — The exclusive accounting date until which this rule applies. If not set, it applies until the end of time.
    generalLedgerAccountCode: "...",  // required — The general ledger account this rule posts the Activity credit or debit to.
    ruleFilter: "..."  // required — The filter syntax for this rule. See https://support.lusid.com/docs/assigning-economic-activity-to-general-ledger-accounts-using-posting-rules for more information on filter syntax.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupersedePostingModuleRuleRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

