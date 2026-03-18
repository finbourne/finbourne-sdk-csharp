# Finbourne.Sdk.Lusid.Model.TransactionConfigurationMovementDataRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MovementTypes** | **string** | Required | . The available values are: Settlement, Traded, StockMovement, FutureCash, Commitment, Receivable, CashSettlement, CashForward, CashCommitment, CashReceivable, Accrual, CashAccrual, ForwardFx, CashFxForward, Carry, CarryAsPnl, VariationMargin, Capital, Fee, LimitAdjustment, BalanceAdjustment, Deferred, CashDeferred |
| **Side** | **string** | Required | The movement side |
| **Direction** | **int** | Required | The movement direction |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties associated with the underlying Movement. |
| **Mappings** | [List&lt;TransactionPropertyMappingRequest&gt;](TransactionPropertyMappingRequest.md) | Optional | This allows you to map a transaction property to a property on the underlying holding. |
| **Name** | **string** | Optional | The movement name (optional) |
| **MovementOptions** | **List&lt;string&gt;** | Optional | Allows extra specifications for the movement. The options currently available are &#39;DirectAdjustment&#39;, &#39;IncludesTradedInterest&#39;, &#39;Virtual&#39;, &#39;Income&#39; and &#39;Expense&#39;. A movement type of &#39;StockMovement&#39; with an option of &#39;DirectAdjusment&#39; will allow you to adjust the units of a holding without affecting its cost base. You will, therefore, be able to reflect the impact of a stock split by loading a Transaction. A movement type of &#39;Carry&#39; with the option as &#39;Expense&#39; will not impact the interest accrual for cash-type holdings such loans, loan facilities and deposits. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionConfigurationMovementDataRequest(
    movementTypes: "...",  // required — . The available values are: Settlement, Traded, StockMovement, FutureCash, Commitment, Receivable, CashSettlement, CashForward, CashCommitment, CashReceivable, Accrual, CashAccrual, ForwardFx, CashFxForward, Carry, CarryAsPnl, VariationMargin, Capital, Fee, LimitAdjustment, BalanceAdjustment, Deferred, CashDeferred
    side: "...",  // required — The movement side
    direction: 0,  // required — The movement direction
    properties: new PerpetualProperty(...),  // optional — The properties associated with the underlying Movement.
    mappings: new List<TransactionPropertyMappingRequest>(),  // optional — This allows you to map a transaction property to a property on the underlying holding.
    name: "...",  // optional — The movement name (optional)
    movementOptions:   // optional — Allows extra specifications for the movement. The options currently available are &#39;DirectAdjustment&#39;, &#39;IncludesTradedInterest&#39;, &#39;Virtual&#39;, &#39;Income&#39; and &#39;Expense&#39;. A movement type of &#39;StockMovement&#39; with an option of &#39;DirectAdjusment&#39; will allow you to adjust the units of a holding without affecting its cost base. You will, therefore, be able to reflect the impact of a stock split by loading a Transaction. A movement type of &#39;Carry&#39; with the option as &#39;Expense&#39; will not impact the interest accrual for cash-type holdings such loans, loan facilities and deposits.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionConfigurationMovementDataRequest>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [TransactionPropertyMappingRequest](TransactionPropertyMappingRequest.md) — used in `Mappings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

