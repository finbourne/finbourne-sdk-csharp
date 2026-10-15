# Finbourne.Sdk.Lusid.Model.PartnerPerformance

The ILPA performance measures for one partner, or for the fund as a whole: paid-in to commitment, the  distribution, residual value and total value multiples, and the net IRR, together with the cash flows the IRR  was solved from. When the fund financed deals through a subscription facility, the measures are also given  with the facility-funded calls re-dated to when the deals were actually funded.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InvestorRecordId** | **string** | Optional | The investor record identifier of the partner, or null when the figures are for the fund as a whole. |
| **Currency** | **string** | Required | The currency the cash flows and residual value are expressed in. |
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
| **WithFacility** | [PartnerPerformanceMeasures](PartnerPerformanceMeasures.md) | Optional | *No description available.* |
| **WithoutFacility** | [PartnerPerformanceMeasures](PartnerPerformanceMeasures.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerPerformance(
    fundId: new ResourceId(...),  // required
    investorRecordId: "...",  // optional — The investor record identifier of the partner, or null when the figures are for the fund as a whole.
    currency: "...",  // required — The currency the cash flows and residual value are expressed in.
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
    residualValueDate: DateTimeOffset.Now,  // required — The date the residual value is taken as at.
    withFacility: new PartnerPerformanceMeasures(...),  // optional
    withoutFacility: new PartnerPerformanceMeasures(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerPerformance>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PartnerPerformanceCashFlow](PartnerPerformanceCashFlow.md) — used in `CashFlows`
- [PartnerPerformanceMeasures](PartnerPerformanceMeasures.md)
- [PartnerPerformanceMeasures](PartnerPerformanceMeasures.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

