# Finbourne.Sdk.Lusid.Model.CashFlowDetail

An individual cashflow inside a cashflow bucket, annotated with the source that produced it  in the cash flow waterfall (SRS > Transaction > Instrument).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Required | The date on which the cashflow is paid. |
| **Amount** | **decimal?** | Optional | The signed amount of the cashflow. A positive amount indicates money is received, a negative amount indicates money is paid. The amount is always the gross (pre-haircut) signed amount; when haircut rules are supplied the haircut and net amounts are reported separately. |
| **Currency** | **string** | Required | The payment currency of the cashflow. |
| **SourceType** | **string** | Required | The source that produced the cashflow in the cash flow waterfall. One of &#39;Instrument&#39; (produced by the valuation engine), &#39;Transaction&#39; (produced from a booked transaction or movement) or &#39;SRS&#39; (sourced from the structured results store). |
| **InstrumentId** | **string** | Required | The LUSID instrument identifier of the instrument that produced the cashflow. |
| **TransactionId** | **string** | Optional | The identifier of the transaction from which the cashflow originates, where known. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **FlowType** | **string** | Optional | The type of the cashflow, e.g. Coupon, Principal or Premium. |
| **PayReceive** | **string** | Optional | Indicates whether the cashflow is paid or received. |
| **GrossAmount** | **decimal?** | Optional | The signed amount of the cashflow before any haircut was applied. Only populated when haircut rules were supplied on the request. |
| **HaircutFraction** | **decimal?** | Optional | The fraction of the gross amount removed by the haircut, in the range [0, 1]. Zero for outflows and for cashflows no rule matched. Only populated when haircut rules were supplied on the request. |
| **NetAmount** | **decimal?** | Optional | The signed amount of the cashflow net of the haircut. Only populated when haircut rules were supplied on the request. |
| **HaircutRuleApplied** | **string** | Optional | The identifier of the haircut rule that was applied to the cashflow, or not present when no rule matched or no haircut rules were supplied on the request. |
| **Error** | **string** | Optional | Only present when the cashflow could not be valued, for example because of missing market data: the valuation error, matching the CashflowError diagnostic reported by the QueryCashFlows endpoint. When set, the amount is null rather than zero. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashFlowDetail(
    paymentDate: DateTimeOffset.Now,  // required — The date on which the cashflow is paid.
    amount: 0.0d,  // optional — The signed amount of the cashflow. A positive amount indicates money is received, a negative amount indicates money is paid. The amount is always the gross (pre-haircut) signed amount; when haircut rules are supplied the haircut and net amounts are reported separately.
    currency: "...",  // required — The payment currency of the cashflow.
    sourceType: "...",  // required — The source that produced the cashflow in the cash flow waterfall. One of &#39;Instrument&#39; (produced by the valuation engine), &#39;Transaction&#39; (produced from a booked transaction or movement) or &#39;SRS&#39; (sourced from the structured results store).
    instrumentId: "...",  // required — The LUSID instrument identifier of the instrument that produced the cashflow.
    transactionId: "...",  // optional — The identifier of the transaction from which the cashflow originates, where known.
    portfolioId: new ResourceId(...),  // required
    flowType: "...",  // optional — The type of the cashflow, e.g. Coupon, Principal or Premium.
    payReceive: "...",  // optional — Indicates whether the cashflow is paid or received.
    grossAmount: 0.0d,  // optional — The signed amount of the cashflow before any haircut was applied. Only populated when haircut rules were supplied on the request.
    haircutFraction: 0.0d,  // optional — The fraction of the gross amount removed by the haircut, in the range [0, 1]. Zero for outflows and for cashflows no rule matched. Only populated when haircut rules were supplied on the request.
    netAmount: 0.0d,  // optional — The signed amount of the cashflow net of the haircut. Only populated when haircut rules were supplied on the request.
    haircutRuleApplied: "...",  // optional — The identifier of the haircut rule that was applied to the cashflow, or not present when no rule matched or no haircut rules were supplied on the request.
    error: "...",  // optional — Only present when the cashflow could not be valued, for example because of missing market data: the valuation error, matching the CashflowError diagnostic reported by the QueryCashFlows endpoint. When set, the amount is null rather than zero.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashFlowDetail>(json);
```

- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

