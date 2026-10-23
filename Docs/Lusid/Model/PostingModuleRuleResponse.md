# Finbourne.Sdk.Lusid.Model.PostingModuleRuleResponse

A version of a Posting rule
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The identifier for the Posting Rule. |
| **GeneralLedgerAccountCode** | **string** | Required | The general ledger account to post the Activity credit or debit to. |
| **RuleFilter** | **string** | Required | The filter syntax for the Posting Rule. See https://support.lusid.com/docs/assigning-economic-activity-to-general-ledger-accounts-using-posting-rules for more information on filter syntax. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The inclusive accounting date from which the Posting Rule applies. If not set, the rule applies from the beginning of time. |
| **EffectiveUntil** | **DateTimeOffset?** | Optional | The exclusive accounting date until which the Posting Rule applies. If not set, the rule applies until the end of time. |
| **VarVersion** | **int** | Optional | The version of the Posting Rule. Starts at 1 and increases each time the rule is superseded. |
| **OriginalRuleId** | **string** | Optional | The identifier of the Posting Rule that this rule was created to supersede, if any. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostingModuleRuleResponse(
    ruleId: "...",  // required — The identifier for the Posting Rule.
    generalLedgerAccountCode: "...",  // required — The general ledger account to post the Activity credit or debit to.
    ruleFilter: "...",  // required — The filter syntax for the Posting Rule. See https://support.lusid.com/docs/assigning-economic-activity-to-general-ledger-accounts-using-posting-rules for more information on filter syntax.
    effectiveFrom: DateTimeOffset.Now,  // optional — The inclusive accounting date from which the Posting Rule applies. If not set, the rule applies from the beginning of time.
    effectiveUntil: DateTimeOffset.Now,  // optional — The exclusive accounting date until which the Posting Rule applies. If not set, the rule applies until the end of time.
    varVersion: 0,  // optional — The version of the Posting Rule. Starts at 1 and increases each time the rule is superseded.
    originalRuleId: "..."  // optional — The identifier of the Posting Rule that this rule was created to supersede, if any.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostingModuleRuleResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

