# Finbourne.Sdk.Lusid.Model.TransactionConfigurationMovementData

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MovementTypes** | **string** | Required | Movement types determine the impact of the movement on the holdings. Available values: Settlement, Traded, StockMovement, FutureCash, Commitment, Receivable, CashSettlement, CashForward, CashCommitment, CashReceivable, Accrual, CashAccrual, ForwardFx, CashFxForward, Carry, CarryAsPnl, VariationMargin, Capital, Fee, LimitAdjustment, BalanceAdjustment, Deferred, CashDeferred. |
| **Side** | **string** | Required | The Side determines which of the fields from our transaction are used to generate the Movement. Side1 means the &#39;security&#39; side of the transaction, ie the Instrument and Units; Side2 means the &#39;cash&#39; side, ie the Total Consideration |
| **Direction** | **int** | Required |  A multiplier to apply to Transaction amounts; the values are -1 to indicate to reverse the signs and 1 to indicate to use the signed values from the Transaction directly. For a typical Transaction with unsigned values, 1 means increase, -1 means decrease |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties associated with the underlying Movement |
| **Mappings** | [List&lt;TransactionPropertyMapping&gt;](TransactionPropertyMapping.md) | Optional | This allows you to map a transaction property to a property on the underlying holding |
| **Name** | **string** | Optional | The movement name (optional) |
| **MovementOptions** | **List&lt;string&gt;** | Optional | Allows extra specifications for the movement. The options currently available are &#39;DirectAdjustment&#39;, &#39;IncludesTradedInterest&#39;, &#39;Virtual&#39;, &#39;Income&#39;, &#39;Expense&#39;, &#39;Bought&#39;, &#39;Sold&#39;, &#39;Coupon&#39;, &#39;Dividend&#39;, &#39;Fee&#39;, &#39;Tax&#39; and &#39;TaxLotAdjustment&#39;. More than one option may be given. A movement type of &#39;StockMovement&#39; with an option of &#39;DirectAdjusment&#39; will allow you to adjust the units of a holding without affecting its cost base. You will, therefore, be able to reflect the impact of a stock split by loading a Transaction. A movement type of &#39;Carry&#39; with the option as &#39;Expense&#39; will not impact the interest accrual for cash-type holdings such loans, loan facilities and deposits. &#39;Bought&#39; and &#39;Sold&#39; declare the direction of traded interest and are only valid alongside &#39;IncludesTradedInterest&#39; on a &#39;Carry&#39; or &#39;CarryAsPnl&#39; movement; without them the direction is inferred from the sign of the amount. &#39;Coupon&#39; and &#39;Dividend&#39; declare the kind of income and are only valid alongside &#39;Income&#39;. &#39;Fee&#39; and &#39;Tax&#39; declare the kind of charge and are valid on &#39;Fee&#39;, &#39;Capital&#39;, &#39;Carry&#39; and &#39;CarryAsPnl&#39; movements; on a &#39;Carry&#39; or &#39;CarryAsPnl&#39; movement they must be declared alongside &#39;Expense&#39;, and they cannot be combined with &#39;Income&#39; or &#39;IncludesTradedInterest&#39;. &#39;Income&#39;, &#39;Expense&#39; and &#39;IncludesTradedInterest&#39; are mutually exclusive, as are &#39;Bought&#39; and &#39;Sold&#39;, &#39;Coupon&#39; and &#39;Dividend&#39;, and &#39;Fee&#39; and &#39;Tax&#39;. &#39;TaxLotAdjustment&#39; is valid only on its own on a &#39;StockMovement&#39;. It sets the amortised cost of the tax lot named by &#39;Transaction/default/TargetTaxlotId&#39;, or apportions one across the holding&#39;s open lots when no lot is named, from &#39;Transaction/default/TargetAmortisedCostPerUnit&#39; or &#39;Transaction/default/TargetIncomeToAmortisePerUnit&#39;, anchored at the transaction&#39;s date or, given in &#39;Transaction/default/AmortisationAnchorDate&#39; for a named lot, at the lot&#39;s amortisation start date, and books no units, cost or cash. The outcome is reported on the output transaction as &#39;Transaction/system/TaxLotAdjustmentResult&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionConfigurationMovementData(
    movementTypes: "...",  // required — Movement types determine the impact of the movement on the holdings. Available values: Settlement, Traded, StockMovement, FutureCash, Commitment, Receivable, CashSettlement, CashForward, CashCommitment, CashReceivable, Accrual, CashAccrual, ForwardFx, CashFxForward, Carry, CarryAsPnl, VariationMargin, Capital, Fee, LimitAdjustment, BalanceAdjustment, Deferred, CashDeferred.
    side: "...",  // required — The Side determines which of the fields from our transaction are used to generate the Movement. Side1 means the &#39;security&#39; side of the transaction, ie the Instrument and Units; Side2 means the &#39;cash&#39; side, ie the Total Consideration
    direction: 0,  // required —  A multiplier to apply to Transaction amounts; the values are -1 to indicate to reverse the signs and 1 to indicate to use the signed values from the Transaction directly. For a typical Transaction with unsigned values, 1 means increase, -1 means decrease
    properties: new PerpetualProperty(...),  // optional — The properties associated with the underlying Movement
    mappings: new List<TransactionPropertyMapping>(),  // optional — This allows you to map a transaction property to a property on the underlying holding
    name: "...",  // optional — The movement name (optional)
    movementOptions:   // optional — Allows extra specifications for the movement. The options currently available are &#39;DirectAdjustment&#39;, &#39;IncludesTradedInterest&#39;, &#39;Virtual&#39;, &#39;Income&#39;, &#39;Expense&#39;, &#39;Bought&#39;, &#39;Sold&#39;, &#39;Coupon&#39;, &#39;Dividend&#39;, &#39;Fee&#39;, &#39;Tax&#39; and &#39;TaxLotAdjustment&#39;. More than one option may be given. A movement type of &#39;StockMovement&#39; with an option of &#39;DirectAdjusment&#39; will allow you to adjust the units of a holding without affecting its cost base. You will, therefore, be able to reflect the impact of a stock split by loading a Transaction. A movement type of &#39;Carry&#39; with the option as &#39;Expense&#39; will not impact the interest accrual for cash-type holdings such loans, loan facilities and deposits. &#39;Bought&#39; and &#39;Sold&#39; declare the direction of traded interest and are only valid alongside &#39;IncludesTradedInterest&#39; on a &#39;Carry&#39; or &#39;CarryAsPnl&#39; movement; without them the direction is inferred from the sign of the amount. &#39;Coupon&#39; and &#39;Dividend&#39; declare the kind of income and are only valid alongside &#39;Income&#39;. &#39;Fee&#39; and &#39;Tax&#39; declare the kind of charge and are valid on &#39;Fee&#39;, &#39;Capital&#39;, &#39;Carry&#39; and &#39;CarryAsPnl&#39; movements; on a &#39;Carry&#39; or &#39;CarryAsPnl&#39; movement they must be declared alongside &#39;Expense&#39;, and they cannot be combined with &#39;Income&#39; or &#39;IncludesTradedInterest&#39;. &#39;Income&#39;, &#39;Expense&#39; and &#39;IncludesTradedInterest&#39; are mutually exclusive, as are &#39;Bought&#39; and &#39;Sold&#39;, &#39;Coupon&#39; and &#39;Dividend&#39;, and &#39;Fee&#39; and &#39;Tax&#39;. &#39;TaxLotAdjustment&#39; is valid only on its own on a &#39;StockMovement&#39;. It sets the amortised cost of the tax lot named by &#39;Transaction/default/TargetTaxlotId&#39;, or apportions one across the holding&#39;s open lots when no lot is named, from &#39;Transaction/default/TargetAmortisedCostPerUnit&#39; or &#39;Transaction/default/TargetIncomeToAmortisePerUnit&#39;, anchored at the transaction&#39;s date or, given in &#39;Transaction/default/AmortisationAnchorDate&#39; for a named lot, at the lot&#39;s amortisation start date, and books no units, cost or cash. The outcome is reported on the output transaction as &#39;Transaction/system/TaxLotAdjustmentResult&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionConfigurationMovementData>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [TransactionPropertyMapping](TransactionPropertyMapping.md) — used in `Mappings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

