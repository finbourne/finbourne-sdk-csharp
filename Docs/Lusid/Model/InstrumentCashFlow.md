# Finbourne.Sdk.Lusid.Model.InstrumentCashFlow

The details for the cashflow associated with an instrument from a given portfolio.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Required | The date at which the given cash flow is due to be paid (SettlementDate is used somewhat interchangeably with PaymentDate.) |
| **Amount** | **decimal?** | Optional | The quantity (amount) that will be paid. Note that this can be empty if the payment is in the future and a model is used that cannot estimate it. |
| **Currency** | **string** | Required | The payment currency of the cash flow. |
| **SourcePortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SourceTransactionId** | **string** | Required | The identifier for the parent transaction on the instrument that will pay/receive this cash flow. |
| **SourceInstrumentScope** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that the holding is in. |
| **SourceInstrumentId** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that the holding is in. |
| **Diagnostics** | **Dictionary&lt;string, string&gt;** | Required | Whilst a cash flow is defined by an (amount,ccy) pair and the date it is paid on there is additional information required for diagnostics. This includes a range of information and can be empty in the case of a simple cash quantity or where further information is not available. Typical information includes items such as reset dates, RIC, accrual start/end, number of days and curve data. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentCashFlow(
    paymentDate: DateTimeOffset.Now,  // required — The date at which the given cash flow is due to be paid (SettlementDate is used somewhat interchangeably with PaymentDate.)
    amount: 0.0d,  // optional — The quantity (amount) that will be paid. Note that this can be empty if the payment is in the future and a model is used that cannot estimate it.
    currency: "...",  // required — The payment currency of the cash flow.
    sourcePortfolioId: new ResourceId(...),  // required
    sourceTransactionId: "...",  // required — The identifier for the parent transaction on the instrument that will pay/receive this cash flow.
    sourceInstrumentScope: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that the holding is in.
    sourceInstrumentId: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that the holding is in.
    diagnostics: ,  // required — Whilst a cash flow is defined by an (amount,ccy) pair and the date it is paid on there is additional information required for diagnostics. This includes a range of information and can be empty in the case of a simple cash quantity or where further information is not available. Typical information includes items such as reset dates, RIC, accrual start/end, number of days and curve data.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentCashFlow>(json);
```

- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

