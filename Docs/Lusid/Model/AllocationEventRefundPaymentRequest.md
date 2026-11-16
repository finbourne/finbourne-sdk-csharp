# Finbourne.Sdk.Lusid.Model.AllocationEventRefundPaymentRequest

The request used to pay out a refund owed to an investor whose receipt against a booked capital call exceeded  what it owed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the refund is paid to. |
| **Amount** | **decimal** | Required | The amount paid, in the event currency. Must be positive, no finer than the currency&#39;s minor unit, and no more than the refund still payable to the investor record on the event. |
| **PaidDate** | **DateTimeOffset** | Required | The date the cash was paid out. Not before the receipt that created the refund payable. |
| **Reference** | **string** | Required | The caller&#39;s reference for the payment, for instance a payment instruction id. Posting the same reference again returns the event unchanged and writes nothing. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventRefundPaymentRequest(
    investorRecordId: "...",  // required — The investor record the refund is paid to.
    amount: 0.0d,  // required — The amount paid, in the event currency. Must be positive, no finer than the currency&#39;s minor unit, and no more than the refund still payable to the investor record on the event.
    paidDate: DateTimeOffset.Now,  // required — The date the cash was paid out. Not before the receipt that created the refund payable.
    reference: "..."  // required — The caller&#39;s reference for the payment, for instance a payment instruction id. Posting the same reference again returns the event unchanged and writes nothing.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventRefundPaymentRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

