# Finbourne.Sdk.Lusid.Model.AllocationEvent

One economic event shared across the participants of an Allocation Map: raised as a draft, computed into  per-investor shares, and finally booked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Description** | **string** | Optional | A description of the Allocation Event. |
| **AllocationMapId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EventType** | **string** | Required | The type of the event: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default, Commitment or DealFunding. Selects the basis rule from the map. A recall is a CapitalCall with a Recall component. A Commitment event is not shared from a basis: its basis values are the signed commitment amounts per commitment line, and they must sum to the amount. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding. |
| **Amount** | **decimal** | Required | The total amount to be shared across the participants. |
| **Currency** | **string** | Required | The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places. |
| **EventDate** | **DateTimeOffset** | Required | The date of the event: the point at which the map, its participants and their basis values are read. |
| **Status** | **string** | Required | The lifecycle status of the event: Draft until its shares are computed, Computed once they are, Booking while its postings are being written, Booked once they all are, and Reversed once a booked event has been backed out. Available values: Draft, Computed, Booked, Booking, Reversed. |
| **BasisSource** | **string** | Optional | Where the basis values came from when the shares were last computed. |
| **Allocations** | [List&lt;AllocationMapAllocation&gt;](AllocationMapAllocation.md) | Required | The per-investor shares of the amount, as last computed. |
| **BookingReference** | **string** | Optional | The reference under which the shares were posted. Set only once the event is booked. |
| **BookedAt** | **DateTimeOffset?** | Optional | The datetime at which the event was booked. |
| **ReallocationReason** | **string** | Optional | The reason given when the event was last recomputed, if it has been. |
| **Components** | [List&lt;AllocationEventComponent&gt;](AllocationEventComponent.md) | Optional | The parts the amount splits into, each shared on its own basis and booked to its own slot. The component amounts must sum to the event amount. Absent means the whole amount is one component: Investment for a CapitalCall, ROC for a Distribution. |
| **Residuals** | [List&lt;AllocationEventRoundingResidual&gt;](AllocationEventRoundingResidual.md) | Optional | The minor units left over when each component&#39;s shares were rounded to the currency, and which investor records took them. |
| **BasisDiagnostics** | [AllocationEventBasisDiagnostics](AllocationEventBasisDiagnostics.md) | Optional | *No description available.* |
| **WrittenIds** | **List&lt;string&gt;** | Optional | The identifiers of the postings the booking has written so far, in write order. Complete once the event is Booked. |
| **BookingErrors** | [List&lt;AllocationEventBookingError&gt;](AllocationEventBookingError.md) | Optional | The postings the booking could not write. Non-empty leaves the event in Booking; book again under the same reference to resume, or unbook to cancel what was written. |
| **Warnings** | [List&lt;AllocationEventBookingWarning&gt;](AllocationEventBookingWarning.md) | Optional | The validation rules the booking was allowed to proceed through under the map&#39;s policy, for instance an OverCall on a map that warns rather than refuses. Kept for the life of the event. |
| **Transfers** | [List&lt;AllocationEventTransfer&gt;](AllocationEventTransfer.md) | Optional | For a Transfer event, the legs to book: each moves a fraction of one capital interest line to another. Required for a Transfer event and not allowed on any other type. The fractions out of one line must sum to at most one; the amount of a Transfer event is zero. |
| **Equalisation** | [AllocationEventEqualisation](AllocationEventEqualisation.md) | Optional | *No description available.* |
| **UseOfProceeds** | [List&lt;AllocationEventUseOfProceeds&gt;](AllocationEventUseOfProceeds.md) | Optional | For a CapitalCall, what the call pays for: rows of purpose, deal and amount that sum to the call amount. An Investment row names a deal the vehicle has funded and is shared under that deal&#39;s participation, with each investor&#39;s share recorded as paid in for that deal; when the deal was funded from a facility the row repays the draw. Not allowed with components or on any other event type. |
| **DealFunding** | [AllocationEventDealFunding](AllocationEventDealFunding.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **ParentAllocationEventId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Replaces** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Reversal** | [AllocationEventReversal](AllocationEventReversal.md) | Optional | *No description available.* |
| **NoticeDate** | **DateTimeOffset?** | Optional | The date the notice went to investors. |
| **DueDate** | **DateTimeOffset?** | Optional | The date the investors&#39; cash is due. |
| **SettlementDate** | **DateTimeOffset?** | Optional | The date the postings settle. Defaults to the event date. |
| **Receipts** | [List&lt;AllocationEventReceipt&gt;](AllocationEventReceipt.md) | Optional | The cash received against the event, in the order it was recorded. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEvent(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    description: "...",  // optional — A description of the Allocation Event.
    allocationMapId: new ResourceId(...),  // required
    eventType: "...",  // required — The type of the event: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default, Commitment or DealFunding. Selects the basis rule from the map. A recall is a CapitalCall with a Recall component. A Commitment event is not shared from a basis: its basis values are the signed commitment amounts per commitment line, and they must sum to the amount. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding.
    amount: 0.0d,  // required — The total amount to be shared across the participants.
    currency: "...",  // required — The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places.
    eventDate: DateTimeOffset.Now,  // required — The date of the event: the point at which the map, its participants and their basis values are read.
    status: "...",  // required — The lifecycle status of the event: Draft until its shares are computed, Computed once they are, Booking while its postings are being written, Booked once they all are, and Reversed once a booked event has been backed out. Available values: Draft, Computed, Booked, Booking, Reversed.
    basisSource: "...",  // optional — Where the basis values came from when the shares were last computed.
    allocations: new List<AllocationMapAllocation>(),  // required — The per-investor shares of the amount, as last computed.
    bookingReference: "...",  // optional — The reference under which the shares were posted. Set only once the event is booked.
    bookedAt: DateTimeOffset.Now,  // optional — The datetime at which the event was booked.
    reallocationReason: "...",  // optional — The reason given when the event was last recomputed, if it has been.
    components: new List<AllocationEventComponent>(),  // optional — The parts the amount splits into, each shared on its own basis and booked to its own slot. The component amounts must sum to the event amount. Absent means the whole amount is one component: Investment for a CapitalCall, ROC for a Distribution.
    residuals: new List<AllocationEventRoundingResidual>(),  // optional — The minor units left over when each component&#39;s shares were rounded to the currency, and which investor records took them.
    basisDiagnostics: new AllocationEventBasisDiagnostics(...),  // optional
    writtenIds: ,  // optional — The identifiers of the postings the booking has written so far, in write order. Complete once the event is Booked.
    bookingErrors: new List<AllocationEventBookingError>(),  // optional — The postings the booking could not write. Non-empty leaves the event in Booking; book again under the same reference to resume, or unbook to cancel what was written.
    warnings: new List<AllocationEventBookingWarning>(),  // optional — The validation rules the booking was allowed to proceed through under the map&#39;s policy, for instance an OverCall on a map that warns rather than refuses. Kept for the life of the event.
    transfers: new List<AllocationEventTransfer>(),  // optional — For a Transfer event, the legs to book: each moves a fraction of one capital interest line to another. Required for a Transfer event and not allowed on any other type. The fractions out of one line must sum to at most one; the amount of a Transfer event is zero.
    equalisation: new AllocationEventEqualisation(...),  // optional
    useOfProceeds: new List<AllocationEventUseOfProceeds>(),  // optional — For a CapitalCall, what the call pays for: rows of purpose, deal and amount that sum to the call amount. An Investment row names a deal the vehicle has funded and is shared under that deal&#39;s participation, with each investor&#39;s share recorded as paid in for that deal; when the deal was funded from a facility the row repays the draw. Not allowed with components or on any other event type.
    dealFunding: new AllocationEventDealFunding(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    parentAllocationEventId: new ResourceId(...),  // optional
    replaces: new ResourceId(...),  // optional
    reversal: new AllocationEventReversal(...),  // optional
    noticeDate: DateTimeOffset.Now,  // optional — The date the notice went to investors.
    dueDate: DateTimeOffset.Now,  // optional — The date the investors&#39; cash is due.
    settlementDate: DateTimeOffset.Now,  // optional — The date the postings settle. Defaults to the event date.
    receipts: new List<AllocationEventReceipt>(),  // optional — The cash received against the event, in the order it was recorded.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEvent>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [AllocationMapAllocation](AllocationMapAllocation.md) — used in `Allocations`
- [AllocationEventComponent](AllocationEventComponent.md) — used in `Components`
- [AllocationEventRoundingResidual](AllocationEventRoundingResidual.md) — used in `Residuals`
- [AllocationEventBasisDiagnostics](AllocationEventBasisDiagnostics.md)
- [AllocationEventBookingError](AllocationEventBookingError.md) — used in `BookingErrors`
- [AllocationEventBookingWarning](AllocationEventBookingWarning.md) — used in `Warnings`
- [AllocationEventTransfer](AllocationEventTransfer.md) — used in `Transfers`
- [AllocationEventEqualisation](AllocationEventEqualisation.md)
- [AllocationEventUseOfProceeds](AllocationEventUseOfProceeds.md) — used in `UseOfProceeds`
- [AllocationEventDealFunding](AllocationEventDealFunding.md)
- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [AllocationEventReversal](AllocationEventReversal.md)
- [AllocationEventReceipt](AllocationEventReceipt.md) — used in `Receipts`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

