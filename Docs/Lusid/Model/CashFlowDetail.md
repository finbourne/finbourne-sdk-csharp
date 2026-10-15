# Finbourne.Sdk.Lusid.Model.CashFlowDetail

An individual cashflow inside a cashflow bucket, annotated with the source that produced it  in the cash flow waterfall (SRS > Transaction > Instrument).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Required | The date on which the cashflow is paid. |
| **Amount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **SourceType** | **string** | Required | The source that produced the cashflow in the cash flow waterfall. One of &#39;Instrument&#39; (produced by the valuation engine), &#39;Transaction&#39; (produced from a booked transaction or movement) or &#39;SRS&#39; (sourced from the structured results store). |
| **InstrumentId** | **string** | Required | The LUSID instrument identifier of the instrument that produced the cashflow. |
| **InstrumentDisplayName** | **string** | Optional | The display name of the instrument that produced the cashflow. Not present when the instrument cannot be resolved (e.g. deleted, no permission). |
| **TransactionId** | **string** | Optional | The identifier of the transaction from which the cashflow originates, where known. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **FlowType** | **string** | Optional | The type of the cashflow, e.g. Coupon, Principal or Premium. |
| **MovementName** | **string** | Optional | The name of the movement that produced the cashflow (e.g. Coupon, Side1), falling back to the flow type when the movement is unnamed. Not present when the cashflow could not be valued. |
| **GrossAmount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **HaircutFraction** | **decimal?** | Optional | The fraction of the gross amount removed by the haircut, in the range [0, 1]. Zero for outflows and for cashflows no rule matched. Only populated when haircut rules were supplied on the request. |
| **NetAmount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **HaircutRuleApplied** | **string** | Optional | The identifier of the haircut rule that was applied to the cashflow, or not present when no rule matched or no haircut rules were supplied on the request. |
| **Error** | **string** | Optional | Present when the cashflow could not be valued, for example because of missing market data: the valuation error, matching the CashflowError diagnostic reported by the QueryCashFlows endpoint. In that case the amount is null rather than zero. Error may also be set when only the report-currency FX lookup failed (see ReportCurrencyAmount), in which case the base Amount remains populated and only ReportCurrencyAmount and TradeToReportCurrencyRate are null. |
| **ReportCurrencyAmount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **TradeToReportCurrencyRate** | **decimal?** | Optional | The FX rate used to convert the cashflow amount from its own payment currency (see Amount) into the request&#39;s report currency. For the default FxSpot rate type it is resolved at the cashflow&#39;s transaction (trade) date, not its payment date; for FxForward it is the forward rate for the payment date (see QueryBucketCashFlowDrillDownRequest.FxRateType and FxRateTypeApplied). Only present when ReportCurrency was supplied on the request; not present when it was omitted, or when the rate could not be resolved (see Error). |
| **FxRateTypeApplied** | **string** | Optional | Which rate type produced TradeToReportCurrencyRate: FxSpot or FxForward. Under the ForwardThenSpot request option this shows whether a cashflow received the forward rate or fell back to spot. Only present when the cashflow was converted into the ReportCurrency. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashFlowDetail(
    paymentDate: DateTimeOffset.Now,  // required — The date on which the cashflow is paid.
    amount: new CurrencyAndAmount(...),  // optional
    sourceType: "...",  // required — The source that produced the cashflow in the cash flow waterfall. One of &#39;Instrument&#39; (produced by the valuation engine), &#39;Transaction&#39; (produced from a booked transaction or movement) or &#39;SRS&#39; (sourced from the structured results store).
    instrumentId: "...",  // required — The LUSID instrument identifier of the instrument that produced the cashflow.
    instrumentDisplayName: "...",  // optional — The display name of the instrument that produced the cashflow. Not present when the instrument cannot be resolved (e.g. deleted, no permission).
    transactionId: "...",  // optional — The identifier of the transaction from which the cashflow originates, where known.
    portfolioId: new ResourceId(...),  // required
    flowType: "...",  // optional — The type of the cashflow, e.g. Coupon, Principal or Premium.
    movementName: "...",  // optional — The name of the movement that produced the cashflow (e.g. Coupon, Side1), falling back to the flow type when the movement is unnamed. Not present when the cashflow could not be valued.
    grossAmount: new CurrencyAndAmount(...),  // optional
    haircutFraction: 0.0d,  // optional — The fraction of the gross amount removed by the haircut, in the range [0, 1]. Zero for outflows and for cashflows no rule matched. Only populated when haircut rules were supplied on the request.
    netAmount: new CurrencyAndAmount(...),  // optional
    haircutRuleApplied: "...",  // optional — The identifier of the haircut rule that was applied to the cashflow, or not present when no rule matched or no haircut rules were supplied on the request.
    error: "...",  // optional — Present when the cashflow could not be valued, for example because of missing market data: the valuation error, matching the CashflowError diagnostic reported by the QueryCashFlows endpoint. In that case the amount is null rather than zero. Error may also be set when only the report-currency FX lookup failed (see ReportCurrencyAmount), in which case the base Amount remains populated and only ReportCurrencyAmount and TradeToReportCurrencyRate are null.
    reportCurrencyAmount: new CurrencyAndAmount(...),  // optional
    tradeToReportCurrencyRate: 0.0d,  // optional — The FX rate used to convert the cashflow amount from its own payment currency (see Amount) into the request&#39;s report currency. For the default FxSpot rate type it is resolved at the cashflow&#39;s transaction (trade) date, not its payment date; for FxForward it is the forward rate for the payment date (see QueryBucketCashFlowDrillDownRequest.FxRateType and FxRateTypeApplied). Only present when ReportCurrency was supplied on the request; not present when it was omitted, or when the rate could not be resolved (see Error).
    fxRateTypeApplied: "...",  // optional — Which rate type produced TradeToReportCurrencyRate: FxSpot or FxForward. Under the ForwardThenSpot request option this shows whether a cashflow received the forward rate or fell back to spot. Only present when the cashflow was converted into the ReportCurrency.
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

- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

