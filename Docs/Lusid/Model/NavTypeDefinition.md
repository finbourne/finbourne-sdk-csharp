# Finbourne.Sdk.Lusid.Model.NavTypeDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The Code for the Nav Type. Must be unique within the Fund. |
| **DisplayName** | **string** | Optional | The Display Name for the Nav Type. Must be unique within the Fund. |
| **Description** | **string** | Optional | The Description for the Nav Type. |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PostingModuleCodes** | **List&lt;string&gt;** | Optional | The Posting Module Codes from which the rules to be applied are retrieved. |
| **CleardownModuleCodes** | **List&lt;string&gt;** | Optional | The Cleardown Module Codes from which the rules to be applied are retrieved. |
| **ValuationRecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **HoldingRecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AccountingMethod** | **string** | Required | Determines the accounting treatment given to the simple position portfolio&#39;s tax lots. A non-default value is required. |
| **SubHoldingKeys** | **List&lt;string&gt;** | Optional | A set of unique transaction properties to group the derived transaction portfolio&#39;s holdings by, perhaps for strategy tagging. Each property must be from the &#39;Transaction&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Transaction/strategies/quantsignal&#39;. See https://support.lusid.com/knowledgebase/article/KA-01879/en-us for more information. |
| **AmortisationMethod** | **string** | Required | The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate |
| **TransactionTypeScope** | **string** | Required | The scope of the transaction types. |
| **CashGainLossCalculationDate** | **string** | Required | The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. A non-default value is required. |
| **AmortisationRuleSetId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **LeaderNavTypeCode** | **string** | Optional | The code of the Nav Type that this Nav Type will follow when set. |
| **TransactionTemplateScope** | **string** | Required | The Transaction Template Scope used by the NavType. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NavTypeDefinition(
    code: "...",  // optional — The Code for the Nav Type. Must be unique within the Fund.
    displayName: "...",  // optional — The Display Name for the Nav Type. Must be unique within the Fund.
    description: "...",  // optional — The Description for the Nav Type.
    chartOfAccountsId: new ResourceId(...),  // required
    postingModuleCodes: ,  // optional — The Posting Module Codes from which the rules to be applied are retrieved.
    cleardownModuleCodes: ,  // optional — The Cleardown Module Codes from which the rules to be applied are retrieved.
    valuationRecipeId: new ResourceId(...),  // required
    holdingRecipeId: new ResourceId(...),  // required
    accountingMethod: "...",  // required — Determines the accounting treatment given to the simple position portfolio&#39;s tax lots. A non-default value is required.
    subHoldingKeys: ,  // optional — A set of unique transaction properties to group the derived transaction portfolio&#39;s holdings by, perhaps for strategy tagging. Each property must be from the &#39;Transaction&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Transaction/strategies/quantsignal&#39;. See https://support.lusid.com/knowledgebase/article/KA-01879/en-us for more information.
    amortisationMethod: "...",  // required — The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate
    transactionTypeScope: "...",  // required — The scope of the transaction types.
    cashGainLossCalculationDate: "...",  // required — The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. A non-default value is required.
    amortisationRuleSetId: new ResourceId(...),  // optional
    leaderNavTypeCode: "...",  // optional — The code of the Nav Type that this Nav Type will follow when set.
    transactionTemplateScope: "..."  // required — The Transaction Template Scope used by the NavType.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NavTypeDefinition>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

