# Finbourne.Sdk.Lusid.Model.PostingModuleRule

A Posting rule
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The identifier for the Posting Rule. |
| **GeneralLedgerAccountCode** | **string** | Required | The general ledger account to post the Activity credit or debit to. |
| **RuleFilter** | **string** | Required | The filter syntax for the Posting Rule. See https://support.lusid.com/knowledgebase/article/KA-02140 for more information on filter syntax. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostingModuleRule(
    ruleId: "...",  // required — The identifier for the Posting Rule.
    generalLedgerAccountCode: "...",  // required — The general ledger account to post the Activity credit or debit to.
    ruleFilter: "..."  // required — The filter syntax for the Posting Rule. See https://support.lusid.com/knowledgebase/article/KA-02140 for more information on filter syntax.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostingModuleRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

