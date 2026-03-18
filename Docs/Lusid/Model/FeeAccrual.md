# Finbourne.Sdk.Lusid.Model.FeeAccrual

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date for which the fee accrual has been calculated. |
| **Code** | **string** | Required | The code of the fee for which the accrual has been calculated. |
| **Name** | **string** | Required | The name of the fee for which the accrual has been calculated. |
| **CalculationBase** | **decimal** | Optional | The result of the evaluating the fee&#39;s calculation base expression. |
| **Amount** | **decimal** | Optional | The result of applying the fee to the calculation base, and scaled down to a day. |
| **PreviousAccrual** | **decimal** | Optional | The previous valuation point&#39;s total accrual. |
| **PreviousTotalAccrual** | **decimal** | Optional | The previous valuation point&#39;s total accrual. |
| **TotalAccrual** | **decimal** | Optional | The sum of the PreviousAccrual and Amount. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeAccrual(
    effectiveAt: DateTimeOffset.Now,  // required — The effective date for which the fee accrual has been calculated.
    code: "...",  // required — The code of the fee for which the accrual has been calculated.
    name: "...",  // required — The name of the fee for which the accrual has been calculated.
    calculationBase: 0.0d,  // optional — The result of the evaluating the fee&#39;s calculation base expression.
    amount: 0.0d,  // optional — The result of applying the fee to the calculation base, and scaled down to a day.
    previousAccrual: 0.0d,  // optional — The previous valuation point&#39;s total accrual.
    previousTotalAccrual: 0.0d,  // optional — The previous valuation point&#39;s total accrual.
    totalAccrual: 0.0d,  // optional — The sum of the PreviousAccrual and Amount.
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

