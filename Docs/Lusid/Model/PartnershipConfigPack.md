# Finbourne.Sdk.Lusid.Model.PartnershipConfigPack

The partnership configuration pack a fund resolves to: the transaction types, chart of accounts and posting rules  the partners' ledger is booked under.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the configuration pack. |
| **Code** | **string** | Required | The code of the configuration pack. |
| **VarVersion** | **string** | Required | The version of the configuration pack. |
| **TransactionTypes** | [List&lt;PackTransactionType&gt;](PackTransactionType.md) | Required | The partnership transaction types the pack provides. |
| **ChartOfAccounts** | [List&lt;PackAccount&gt;](PackAccount.md) | Required | The accounts the pack posts partner capital to. |
| **PostingRules** | [List&lt;PackPostingRule&gt;](PackPostingRule.md) | Required | The rules that move each transaction type between its accounts. |
| **GeneralLedgerProfileCode** | **string** | Optional | The code of the general ledger profile the pack&#39;s posting rules belong to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnershipConfigPack(
    scope: "...",  // required — The scope of the configuration pack.
    code: "...",  // required — The code of the configuration pack.
    varVersion: "...",  // required — The version of the configuration pack.
    transactionTypes: new List<PackTransactionType>(),  // required — The partnership transaction types the pack provides.
    chartOfAccounts: new List<PackAccount>(),  // required — The accounts the pack posts partner capital to.
    postingRules: new List<PackPostingRule>(),  // required — The rules that move each transaction type between its accounts.
    generalLedgerProfileCode: "..."  // optional — The code of the general ledger profile the pack&#39;s posting rules belong to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnershipConfigPack>(json);
```

- [PackTransactionType](PackTransactionType.md) — used in `TransactionTypes`
- [PackAccount](PackAccount.md) — used in `ChartOfAccounts`
- [PackPostingRule](PackPostingRule.md) — used in `PostingRules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

