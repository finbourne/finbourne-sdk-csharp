# Finbourne.Sdk.Lusid.Model.AllocationEventNotice

A capital call or distribution notice for one partner on an allocation event: the lines allocated to the  partner, the net amount due, the partner's unfunded commitment rolled through the event, cumulative balances  for the partner and the general partner, and a DRAFT watermark while the event is not yet booked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Fund** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Event** | [AllocationEventNoticeEvent](AllocationEventNoticeEvent.md) | Required | *No description available.* |
| **Partner** | [AllocationEventNoticePartner](AllocationEventNoticePartner.md) | Required | *No description available.* |
| **Currency** | **string** | Required | The currency the notice amounts are expressed in. |
| **Lines** | [List&lt;AllocationEventNoticeLine&gt;](AllocationEventNoticeLine.md) | Required | The notice lines, one per component of the partner&#39;s allocation. |
| **NetAmountDue** | **decimal** | Required | The net amount due, positive when the partner pays the fund and negative when the fund pays the partner. |
| **UnfundedReconciliation** | [AllocationEventNoticeUnfundedReconciliation](AllocationEventNoticeUnfundedReconciliation.md) | Required | *No description available.* |
| **Cumulative** | [AllocationEventNoticeCumulative](AllocationEventNoticeCumulative.md) | Required | *No description available.* |
| **GpColumn** | [AllocationEventNoticeCumulative](AllocationEventNoticeCumulative.md) | Optional | *No description available.* |
| **Wire** | [AllocationEventNoticeWire](AllocationEventNoticeWire.md) | Optional | *No description available.* |
| **PaymentHold** | [AllocationPaymentHold](AllocationPaymentHold.md) | Optional | *No description available.* |
| **Watermark** | **string** | Optional | DRAFT until the allocation event is booked, otherwise null. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNotice(
    fund: new ResourceId(...),  // required
    varEvent: new AllocationEventNoticeEvent(...),  // required
    partner: new AllocationEventNoticePartner(...),  // required
    currency: "...",  // required — The currency the notice amounts are expressed in.
    lines: new List<AllocationEventNoticeLine>(),  // required — The notice lines, one per component of the partner&#39;s allocation.
    netAmountDue: 0.0d,  // required — The net amount due, positive when the partner pays the fund and negative when the fund pays the partner.
    unfundedReconciliation: new AllocationEventNoticeUnfundedReconciliation(...),  // required
    cumulative: new AllocationEventNoticeCumulative(...),  // required
    gpColumn: new AllocationEventNoticeCumulative(...),  // optional
    wire: new AllocationEventNoticeWire(...),  // optional
    paymentHold: new AllocationPaymentHold(...),  // optional
    watermark: "..."  // optional — DRAFT until the allocation event is booked, otherwise null.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNotice>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [AllocationEventNoticeEvent](AllocationEventNoticeEvent.md)
- [AllocationEventNoticePartner](AllocationEventNoticePartner.md)
- [AllocationEventNoticeLine](AllocationEventNoticeLine.md) — used in `Lines`
- [AllocationEventNoticeUnfundedReconciliation](AllocationEventNoticeUnfundedReconciliation.md)
- [AllocationEventNoticeCumulative](AllocationEventNoticeCumulative.md)
- [AllocationEventNoticeCumulative](AllocationEventNoticeCumulative.md)
- [AllocationEventNoticeWire](AllocationEventNoticeWire.md)
- [AllocationPaymentHold](AllocationPaymentHold.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

