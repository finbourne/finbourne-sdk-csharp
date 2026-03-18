# Finbourne.Sdk.Lusid.Model.CleardownModuleRule

A Cleardown rule
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The identifier for the Cleardown Rule. |
| **GeneralLedgerAccountCode** | **string** | Required | The account to post the residual P&amp;L to. |
| **RuleFilter** | **string** | Required | The filter syntax for the Cleardown Rule. See https://support.lusid.com/knowledgebase/article/KA-02140 for more information on filter syntax. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CleardownModuleRule(
    ruleId: "...",  // required — The identifier for the Cleardown Rule.
    generalLedgerAccountCode: "...",  // required — The account to post the residual P&amp;L to.
    ruleFilter: "..."  // required — The filter syntax for the Cleardown Rule. See https://support.lusid.com/knowledgebase/article/KA-02140 for more information on filter syntax.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CleardownModuleRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

