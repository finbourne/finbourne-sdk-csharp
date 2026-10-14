# Finbourne.Sdk.Lusid.Model.AllocationEventReceipt

One receipt of cash against a booked capital call, as recorded.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Optional | The investor record the cash came from. |
| **Amount** | **decimal** | Optional | The cash received, in the event currency after any FX conversion. |
| **ReceiptDate** | **DateTimeOffset** | Optional | The date the cash was received. |
| **Applied** | **decimal** | Optional | How much of the receipt was applied to what the investor owed. |
| **Refund** | **decimal** | Optional | How much of the receipt exceeded what the investor owed and became a refund payable. |
| **PaymentCurrency** | **string** | Optional | The ISO 4217 code of the currency the cash arrived in, when it differs from the event currency. |
| **PaymentFxRate** | **decimal?** | Optional | The rate the payment was converted at, as units of event currency per unit of payment currency. Required with a payment currency. |
| **FxDifference** | **decimal** | Optional | The part of the difference between the payment converted at the notice rate and at the payment rate that the fund did not absorb; positive when the rate moved against the fund. Zero without a notice rate. |
| **BankCharge** | **decimal** | Optional | Any bank charge deducted from the cash before it arrived, in the event currency. |
| **BankChargeBearer** | **string** | Optional | Who bears the bank charge: Partner leaves it outstanding on the investor, Fund books it as a fund expense. Defaults to the map&#39;s policy. |
| **ShortfallWrittenOff** | **decimal** | Optional | Any small shortfall within the map&#39;s tolerance that was written off rather than left outstanding. |
| **PostingId** | **string** | Optional | The identifier of the receipt posting on the investor&#39;s line. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventReceipt(
    investorRecordId: "...",  // optional — The investor record the cash came from.
    amount: 0.0d,  // optional — The cash received, in the event currency after any FX conversion.
    receiptDate: DateTimeOffset.Now,  // optional — The date the cash was received.
    applied: 0.0d,  // optional — How much of the receipt was applied to what the investor owed.
    refund: 0.0d,  // optional — How much of the receipt exceeded what the investor owed and became a refund payable.
    paymentCurrency: "...",  // optional — The ISO 4217 code of the currency the cash arrived in, when it differs from the event currency.
    paymentFxRate: 0.0d,  // optional — The rate the payment was converted at, as units of event currency per unit of payment currency. Required with a payment currency.
    fxDifference: 0.0d,  // optional — The part of the difference between the payment converted at the notice rate and at the payment rate that the fund did not absorb; positive when the rate moved against the fund. Zero without a notice rate.
    bankCharge: 0.0d,  // optional — Any bank charge deducted from the cash before it arrived, in the event currency.
    bankChargeBearer: "...",  // optional — Who bears the bank charge: Partner leaves it outstanding on the investor, Fund books it as a fund expense. Defaults to the map&#39;s policy.
    shortfallWrittenOff: 0.0d,  // optional — Any small shortfall within the map&#39;s tolerance that was written off rather than left outstanding.
    postingId: "..."  // optional — The identifier of the receipt posting on the investor&#39;s line.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventReceipt>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

