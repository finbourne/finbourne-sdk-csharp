# Finbourne.Sdk.Lusid.Model.AllocationEventReceiptRequest

The request used to record cash received from an investor against a booked capital call.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the cash came from. |
| **Amount** | **decimal** | Required | The cash the partner sent, as sent and before any bank charge: in the payment currency if one is given and otherwise in the event currency. |
| **ReceiptDate** | **DateTimeOffset** | Required | The date the cash was received. |
| **PaymentCurrency** | **string** | Optional | The ISO 4217 code of the currency the cash arrived in, when it differs from the event currency. |
| **PaymentFxRate** | **decimal?** | Optional | The rate the payment was converted at, as units of event currency per unit of payment currency. Required with a payment currency. |
| **NoticeFxRate** | **decimal?** | Optional | The rate the call was noticed at in the payment currency, in the same terms as the payment FX rate. With one, only the rate&#39;s effect on the payment is an FX difference; without one a payment converting to less than the call is simply short. Only with a payment currency. |
| **BankCharge** | **decimal** | Optional | Any bank charge deducted from the cash before it arrived, in the event currency. |
| **BankChargeBearer** | **string** | Optional | Who bears the bank charge: Partner leaves it outstanding on the investor, Fund books it as a fund expense. Defaults to the map&#39;s policy. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventReceiptRequest(
    investorRecordId: "...",  // required — The investor record the cash came from.
    amount: 0.0d,  // required — The cash the partner sent, as sent and before any bank charge: in the payment currency if one is given and otherwise in the event currency.
    receiptDate: DateTimeOffset.Now,  // required — The date the cash was received.
    paymentCurrency: "...",  // optional — The ISO 4217 code of the currency the cash arrived in, when it differs from the event currency.
    paymentFxRate: 0.0d,  // optional — The rate the payment was converted at, as units of event currency per unit of payment currency. Required with a payment currency.
    noticeFxRate: 0.0d,  // optional — The rate the call was noticed at in the payment currency, in the same terms as the payment FX rate. With one, only the rate&#39;s effect on the payment is an FX difference; without one a payment converting to less than the call is simply short. Only with a payment currency.
    bankCharge: 0.0d,  // optional — Any bank charge deducted from the cash before it arrived, in the event currency.
    bankChargeBearer: "..."  // optional — Who bears the bank charge: Partner leaves it outstanding on the investor, Fund books it as a fund expense. Defaults to the map&#39;s policy.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventReceiptRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

