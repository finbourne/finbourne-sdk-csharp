# Finbourne.Sdk.Lusid.Model.FeeAccrual

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date for which the fee accrual has been calculated. |
| **Code** | **string** | Required | The code of the fee for which the accrual has been calculated. |
| **Name** | **string** | Required | The name of the fee for which the accrual has been calculated. |
| **CalculationBase** | **decimal** | Optional | The basis the annual accrual derives from: the result of evaluating the fee&#39;s calculation base expression, or the configured annual amount for a fixed-amount fee. |
| **Amount** | **decimal** | Optional | The result of applying the fee to the calculation base, and scaled down to a day. |
| **PreviousAccrual** | **decimal** | Optional | The previous valuation point&#39;s total accrual. |
| **PreviousTotalAccrual** | **decimal** | Optional | The previous valuation point&#39;s total accrual. |
| **TotalAccrual** | **decimal** | Optional | The sum of the PreviousAccrual and Amount. |
| **CapPeriodAccrual** | **decimal** | Optional | The amount accrued so far in the current fee year (from the fee&#39;s AnchorDate), in the fund currency, against which an annual FeeCap is assessed. |
| **FeeCapApplied** | **bool** | Optional | Whether the FeeCap reduced the amount accrued at this valuation point. |
| **FeeFloorApplied** | **bool** | Optional | Whether the FeeFloor raised the amount accrued at this valuation point. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeAccrual(
    effectiveAt: DateTimeOffset.Now,  // required — The effective date for which the fee accrual has been calculated.
    code: "...",  // required — The code of the fee for which the accrual has been calculated.
    name: "...",  // required — The name of the fee for which the accrual has been calculated.
    calculationBase: 0.0d,  // optional — The basis the annual accrual derives from: the result of evaluating the fee&#39;s calculation base expression, or the configured annual amount for a fixed-amount fee.
    amount: 0.0d,  // optional — The result of applying the fee to the calculation base, and scaled down to a day.
    previousAccrual: 0.0d,  // optional — The previous valuation point&#39;s total accrual.
    previousTotalAccrual: 0.0d,  // optional — The previous valuation point&#39;s total accrual.
    totalAccrual: 0.0d,  // optional — The sum of the PreviousAccrual and Amount.
    capPeriodAccrual: 0.0d,  // optional — The amount accrued so far in the current fee year (from the fee&#39;s AnchorDate), in the fund currency, against which an annual FeeCap is assessed.
    feeCapApplied: true,  // optional — Whether the FeeCap reduced the amount accrued at this valuation point.
    feeFloorApplied: true,  // optional — Whether the FeeFloor raised the amount accrued at this valuation point.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeAccrual>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

