# Finbourne.Sdk.Lusid.Model.AllocationEvent

One economic event shared across the participants of an Allocation Map: raised as a draft, computed into  per-investor shares, and finally booked.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Description** | **string** | Optional | A description of the Allocation Event. |
| **AllocationMapId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EventType** | **string** | Required | The type of the event: CapitalCall, Distribution, FeeExpense or ValuationMove. Selects the basis rule from the map. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove. |
| **Amount** | **decimal** | Required | The total amount to be shared across the participants. |
| **Currency** | **string** | Required | The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places. |
| **EventDate** | **DateTimeOffset** | Required | The date of the event: the point at which the map, its participants and their basis values are read. |
| **Status** | **string** | Required | The lifecycle status of the event: Draft until its shares are computed, Computed once they are, and Booked once posted. Available values: Draft, Computed, Booked. |
| **BasisSource** | **string** | Optional | Where the basis values came from when the shares were last computed. |
| **Allocations** | [List&lt;AllocationMapAllocation&gt;](AllocationMapAllocation.md) | Required | The per-investor shares of the amount, as last computed. |
| **BookingReference** | **string** | Optional | The reference under which the shares were posted. Set only once the event is booked. |
| **BookedAt** | **DateTimeOffset?** | Optional | The datetime at which the event was booked. |
| **ReallocationReason** | **string** | Optional | The reason given when the event was last recomputed, if it has been. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
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
    eventType: "...",  // required — The type of the event: CapitalCall, Distribution, FeeExpense or ValuationMove. Selects the basis rule from the map. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove.
    amount: 0.0d,  // required — The total amount to be shared across the participants.
    currency: "...",  // required — The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places.
    eventDate: DateTimeOffset.Now,  // required — The date of the event: the point at which the map, its participants and their basis values are read.
    status: "...",  // required — The lifecycle status of the event: Draft until its shares are computed, Computed once they are, and Booked once posted. Available values: Draft, Computed, Booked.
    basisSource: "...",  // optional — Where the basis values came from when the shares were last computed.
    allocations: new List<AllocationMapAllocation>(),  // required — The per-investor shares of the amount, as last computed.
    bookingReference: "...",  // optional — The reference under which the shares were posted. Set only once the event is booked.
    bookedAt: DateTimeOffset.Now,  // optional — The datetime at which the event was booked.
    reallocationReason: "...",  // optional — The reason given when the event was last recomputed, if it has been.
    varVersion: new ModelVersion(...),  // optional
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
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

