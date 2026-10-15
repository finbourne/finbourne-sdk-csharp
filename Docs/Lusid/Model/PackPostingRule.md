# Finbourne.Sdk.Lusid.Model.PackPostingRule

A posting rule on a partnership configuration pack.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The posting rule identifier. |
| **TransactionType** | **string** | Required | The transaction type. |
| **DebitAccount** | **string** | Required | The account debited. |
| **CreditAccount** | **string** | Required | The account credited. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PackPostingRule(
    ruleId: "...",  // required — The posting rule identifier.
    transactionType: "...",  // required — The transaction type.
    debitAccount: "...",  // required — The account debited.
    creditAccount: "..."  // required — The account credited.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PackPostingRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

