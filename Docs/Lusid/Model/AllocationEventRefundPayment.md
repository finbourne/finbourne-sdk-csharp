# Finbourne.Sdk.Lusid.Model.AllocationEventRefundPayment

One payment of a refund owed to an investor record on a booked capital call, as recorded.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Optional | The investor record the refund is paid to. |
| **Amount** | **decimal** | Optional | The amount paid, in the event currency. Must be positive, no finer than the currency&#39;s minor unit, and no more than the refund still payable to the investor record on the event. |
| **PaidDate** | **DateTimeOffset** | Optional | The date the cash was paid out. Not before the receipt that created the refund payable. |
| **Reference** | **string** | Optional | The caller&#39;s reference for the payment, for instance a payment instruction id. Posting the same reference again returns the event unchanged and writes nothing. |
| **PostingId** | **string** | Optional | The identifier of the fund-side posting the payment was written under. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventRefundPayment(
    investorRecordId: "...",  // optional — The investor record the refund is paid to.
    amount: 0.0d,  // optional — The amount paid, in the event currency. Must be positive, no finer than the currency&#39;s minor unit, and no more than the refund still payable to the investor record on the event.
    paidDate: DateTimeOffset.Now,  // optional — The date the cash was paid out. Not before the receipt that created the refund payable.
    reference: "...",  // optional — The caller&#39;s reference for the payment, for instance a payment instruction id. Posting the same reference again returns the event unchanged and writes nothing.
    postingId: "..."  // optional — The identifier of the fund-side posting the payment was written under.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventRefundPayment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

