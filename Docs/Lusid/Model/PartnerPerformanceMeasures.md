# Finbourne.Sdk.Lusid.Model.PartnerPerformanceMeasures

One set of performance measures: the multiples, the net IRR and the cash flows it was solved from.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Commitment** | **decimal** | Required | The total commitment the paid-in-capital ratio is measured against. |
| **PaidIn** | **decimal** | Required | The contributions paid in to the fund. |
| **Distributed** | **decimal** | Required | The distributions paid out of the fund. |
| **Pic** | **decimal?** | Optional | Paid-in capital as a multiple of commitment, or null when there is no commitment. |
| **Dpi** | **decimal?** | Optional | Distributions as a multiple of paid-in capital, or null when nothing has been paid in. |
| **Rvpi** | **decimal?** | Optional | Residual value as a multiple of paid-in capital, or null when nothing has been paid in. |
| **Tvpi** | **decimal?** | Optional | Total value as a multiple of paid-in capital, being DPI plus RVPI. |
| **NetIrr** | **decimal?** | Optional | The annualised net internal rate of return solved from the dated cash flows, or null when no rate can be solved. |
| **CashFlows** | [List&lt;PartnerPerformanceCashFlow&gt;](PartnerPerformanceCashFlow.md) | Required | The dated cash flows the net IRR was solved from, including the terminal residual value. |
| **ResidualValue** | **decimal** | Required | The partner&#39;s residual value in the fund at the valuation date. |
| **ResidualValueDate** | **DateTimeOffset** | Required | The date the residual value is taken as at. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerPerformanceMeasures(
    commitment: 0.0d,  // required — The total commitment the paid-in-capital ratio is measured against.
    paidIn: 0.0d,  // required — The contributions paid in to the fund.
    distributed: 0.0d,  // required — The distributions paid out of the fund.
    pic: 0.0d,  // optional — Paid-in capital as a multiple of commitment, or null when there is no commitment.
    dpi: 0.0d,  // optional — Distributions as a multiple of paid-in capital, or null when nothing has been paid in.
    rvpi: 0.0d,  // optional — Residual value as a multiple of paid-in capital, or null when nothing has been paid in.
    tvpi: 0.0d,  // optional — Total value as a multiple of paid-in capital, being DPI plus RVPI.
    netIrr: 0.0d,  // optional — The annualised net internal rate of return solved from the dated cash flows, or null when no rate can be solved.
    cashFlows: new List<PartnerPerformanceCashFlow>(),  // required — The dated cash flows the net IRR was solved from, including the terminal residual value.
    residualValue: 0.0d,  // required — The partner&#39;s residual value in the fund at the valuation date.
    residualValueDate: DateTimeOffset.Now  // required — The date the residual value is taken as at.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerPerformanceMeasures>(json);
```

- [PartnerPerformanceCashFlow](PartnerPerformanceCashFlow.md) — used in `CashFlows`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

