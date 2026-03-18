# Finbourne.Sdk.Lusid.Model.InstrumentPaymentDiaryRow

An individual row containing details of a single cashflow in the diary.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Optional | The quantity (amount) that will be paid. Note that this can be empty if the payment is in the future and a model is used that cannot estimate it. |
| **Currency** | **string** | Optional | The payment currency of the cash flow. |
| **PaymentDate** | **DateTimeOffset** | Optional | The date at which the given cash flow is due to be paid. |
| **PayOrReceive** | **string** | Optional | Does the cash flow belong to the Pay or Receive leg. |
| **AccrualStart** | **DateTimeOffset** | Optional | The date on which accruals start for this cashflow. |
| **AccrualEnd** | **DateTimeOffset** | Optional | The date on which accruals end for this cashflow. |
| **CashFlowType** | **string** | Optional | The type of cashflow. |
| **IsCashFlowDetermined** | **bool** | Optional | Is the cashflow determined as of the effective date time. |
| **IsCashFlowHistoric** | **bool** | Optional | Has the cashflow been paid, i.e. has it become a historic cashflow, as of the date and time pointed to be effectiveAt. |
| **DiscountFactor** | **decimal** | Optional | Weighting factor to discount cashflow to the present value. |
| **DiscountedExpectedCashFlowAmount** | **decimal** | Optional | The expected cashflow amount taking into account the discount factor. |
| **DayCountFraction** | **decimal?** | Optional | The day count fraction, if appropriate. |
| **ForwardRate** | **decimal?** | Optional | Forward rate for cash flow if appropriate. (as in for a rates fixed or floating leg) |
| **ResetRate** | **decimal?** | Optional | The value of the reset, if any. |
| **Spread** | **decimal?** | Optional | The spread that exists on the payoff. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentPaymentDiaryRow(
    quantity: 0.0d,  // optional — The quantity (amount) that will be paid. Note that this can be empty if the payment is in the future and a model is used that cannot estimate it.
    currency: "...",  // optional — The payment currency of the cash flow.
    paymentDate: DateTimeOffset.Now,  // optional — The date at which the given cash flow is due to be paid.
    payOrReceive: "...",  // optional — Does the cash flow belong to the Pay or Receive leg.
    accrualStart: DateTimeOffset.Now,  // optional — The date on which accruals start for this cashflow.
    accrualEnd: DateTimeOffset.Now,  // optional — The date on which accruals end for this cashflow.
    cashFlowType: "...",  // optional — The type of cashflow.
    isCashFlowDetermined: true,  // optional — Is the cashflow determined as of the effective date time.
    isCashFlowHistoric: true,  // optional — Has the cashflow been paid, i.e. has it become a historic cashflow, as of the date and time pointed to be effectiveAt.
    discountFactor: 0.0d,  // optional — Weighting factor to discount cashflow to the present value.
    discountedExpectedCashFlowAmount: 0.0d,  // optional — The expected cashflow amount taking into account the discount factor.
    dayCountFraction: 0.0d,  // optional — The day count fraction, if appropriate.
    forwardRate: 0.0d,  // optional — Forward rate for cash flow if appropriate. (as in for a rates fixed or floating leg)
    resetRate: 0.0d,  // optional — The value of the reset, if any.
    spread: 0.0d  // optional — The spread that exists on the payoff.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentPaymentDiaryRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

