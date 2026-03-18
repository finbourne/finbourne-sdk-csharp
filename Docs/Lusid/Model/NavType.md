# Finbourne.Sdk.Lusid.Model.NavType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | *No description available.* |
| **Code** | **string** | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **ChartOfAccountsId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PostingModuleCodes** | **List&lt;string&gt;** | Optional | *No description available.* |
| **CleardownModuleCodes** | **List&lt;string&gt;** | Optional | *No description available.* |
| **ValuationRecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **HoldingRecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AccountingMethod** | **string** | Required | *No description available.* |
| **SubHoldingKeys** | **List&lt;string&gt;** | Optional | Set of unique holding identifiers, e.g. trader, desk, strategy. |
| **AmortisationMethod** | **string** | Required | *No description available.* |
| **TransactionTypeScope** | **string** | Required | *No description available.* |
| **CashGainLossCalculationDate** | **string** | Required | *No description available.* |
| **AmortisationRuleSetId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **LeaderNavTypeCode** | **string** | Optional | *No description available.* |
| **TransactionTemplateScope** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NavType(
    status: "...",  // required
    code: "...",  // optional
    displayName: "...",  // optional
    description: "...",  // optional
    chartOfAccountsId: new ResourceId(...),  // required
    postingModuleCodes: ,  // optional
    cleardownModuleCodes: ,  // optional
    valuationRecipeId: new ResourceId(...),  // required
    holdingRecipeId: new ResourceId(...),  // required
    accountingMethod: "...",  // required
    subHoldingKeys: ,  // optional — Set of unique holding identifiers, e.g. trader, desk, strategy.
    amortisationMethod: "...",  // required
    transactionTypeScope: "...",  // required
    cashGainLossCalculationDate: "...",  // required
    amortisationRuleSetId: new ResourceId(...),  // optional
    leaderNavTypeCode: "...",  // optional
    transactionTemplateScope: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NavType>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

