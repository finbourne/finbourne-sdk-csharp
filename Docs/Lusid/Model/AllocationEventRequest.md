# Finbourne.Sdk.Lusid.Model.AllocationEventRequest

The request used to raise or replace an Allocation Event. The event is computed against its map straight away.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Allocation Event. Together with the scope this uniquely identifies the event. |
| **AllocationMapId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EventType** | **string** | Required | The type of the event: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default, Commitment or DealFunding. Selects the basis rule from the map. A recall is a CapitalCall with a Recall component. A Commitment event is not shared from a basis: its basis values are the signed commitment amounts per commitment line, and they must sum to the amount. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding. |
| **Amount** | **decimal** | Required | The total amount to be shared across the participants. |
| **Currency** | **string** | Required | The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places. |
| **EventDate** | **DateTimeOffset** | Required | The date of the event: the point at which the map, its participants and their basis values are read. |
| **Description** | **string** | Optional | A description of the Allocation Event. |
| **BasisValues** | [List&lt;AllocationMapBasisValue&gt;](AllocationMapBasisValue.md) | Optional | Optional basis values per investor record, used when the map&#39;s basis is not resolvable from stored data. |
| **Components** | [List&lt;AllocationEventComponent&gt;](AllocationEventComponent.md) | Optional | The parts the amount splits into, each shared on its own basis and booked to its own slot. The component amounts must sum to the event amount. Absent means the whole amount is one component: Investment for a CapitalCall, ROC for a Distribution. |
| **Transfers** | [List&lt;AllocationEventTransfer&gt;](AllocationEventTransfer.md) | Optional | For a Transfer event, the legs to book: each moves a fraction of one capital interest line to another. Required for a Transfer event and not allowed on any other type. The fractions out of one line must sum to at most one; the amount of a Transfer event is zero. |
| **Equalisation** | [AllocationEventEqualisation](AllocationEventEqualisation.md) | Optional | *No description available.* |
| **UseOfProceeds** | [List&lt;AllocationEventUseOfProceeds&gt;](AllocationEventUseOfProceeds.md) | Optional | For a CapitalCall, what the call pays for: rows of purpose, deal and amount that sum to the call amount. An Investment row names a deal the vehicle has funded and is shared under that deal&#39;s participation, with each investor&#39;s share recorded as paid in for that deal; when the deal was funded from a facility the row repays the draw. Not allowed with components or on any other event type. |
| **DealFunding** | [AllocationEventDealFunding](AllocationEventDealFunding.md) | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime at which the event is created or replaced. Defaults to the earliest effective time on create and the current LUSID system datetime on replace. |
| **Replaces** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **NoticeDate** | **DateTimeOffset?** | Optional | The date the notice went to investors. |
| **DueDate** | **DateTimeOffset?** | Optional | The date the investors&#39; cash is due. |
| **SettlementDate** | **DateTimeOffset?** | Optional | The date the postings settle. Defaults to the event date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventRequest(
    code: "...",  // required — The code of the Allocation Event. Together with the scope this uniquely identifies the event.
    allocationMapId: new ResourceId(...),  // required
    eventType: "...",  // required — The type of the event: CapitalCall, Distribution, FeeExpense, ValuationMove, Equalisation, RecallExpiry, Transfer, Default, Commitment or DealFunding. Selects the basis rule from the map. A recall is a CapitalCall with a Recall component. A Commitment event is not shared from a basis: its basis values are the signed commitment amounts per commitment line, and they must sum to the amount. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove, Commitment, Equalisation, RecallExpiry, Transfer, Default, DealFunding.
    amount: 0.0d,  // required — The total amount to be shared across the participants.
    currency: "...",  // required — The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places.
    eventDate: DateTimeOffset.Now,  // required — The date of the event: the point at which the map, its participants and their basis values are read.
    description: "...",  // optional — A description of the Allocation Event.
    basisValues: new List<AllocationMapBasisValue>(),  // optional — Optional basis values per investor record, used when the map&#39;s basis is not resolvable from stored data.
    components: new List<AllocationEventComponent>(),  // optional — The parts the amount splits into, each shared on its own basis and booked to its own slot. The component amounts must sum to the event amount. Absent means the whole amount is one component: Investment for a CapitalCall, ROC for a Distribution.
    transfers: new List<AllocationEventTransfer>(),  // optional — For a Transfer event, the legs to book: each moves a fraction of one capital interest line to another. Required for a Transfer event and not allowed on any other type. The fractions out of one line must sum to at most one; the amount of a Transfer event is zero.
    equalisation: new AllocationEventEqualisation(...),  // optional
    useOfProceeds: new List<AllocationEventUseOfProceeds>(),  // optional — For a CapitalCall, what the call pays for: rows of purpose, deal and amount that sum to the call amount. An Investment row names a deal the vehicle has funded and is shared under that deal&#39;s participation, with each investor&#39;s share recorded as paid in for that deal; when the deal was funded from a facility the row repays the draw. Not allowed with components or on any other event type.
    dealFunding: new AllocationEventDealFunding(...),  // optional
    effectiveAt: DateTimeOffset.Now,  // optional — The effective datetime at which the event is created or replaced. Defaults to the earliest effective time on create and the current LUSID system datetime on replace.
    replaces: new ResourceId(...),  // optional
    noticeDate: DateTimeOffset.Now,  // optional — The date the notice went to investors.
    dueDate: DateTimeOffset.Now,  // optional — The date the investors&#39; cash is due.
    settlementDate: DateTimeOffset.Now  // optional — The date the postings settle. Defaults to the event date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventRequest>(json);
```

- [ResourceId](ResourceId.md)
- [AllocationMapBasisValue](AllocationMapBasisValue.md) — used in `BasisValues`
- [AllocationEventComponent](AllocationEventComponent.md) — used in `Components`
- [AllocationEventTransfer](AllocationEventTransfer.md) — used in `Transfers`
- [AllocationEventEqualisation](AllocationEventEqualisation.md)
- [AllocationEventUseOfProceeds](AllocationEventUseOfProceeds.md) — used in `UseOfProceeds`
- [AllocationEventDealFunding](AllocationEventDealFunding.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

