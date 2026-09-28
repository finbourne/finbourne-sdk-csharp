# Finbourne.Sdk.Lusid.Model.AllocationEventRequest

The request used to raise or replace an Allocation Event. The event is computed against its map straight away.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Allocation Event. Together with the scope this uniquely identifies the event. |
| **AllocationMapId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EventType** | **string** | Required | The type of the event: CapitalCall, Distribution, FeeExpense or ValuationMove. Selects the basis rule from the map. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove. |
| **Amount** | **decimal** | Required | The total amount to be shared across the participants. |
| **Currency** | **string** | Required | The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places. |
| **EventDate** | **DateTimeOffset** | Required | The date of the event: the point at which the map, its participants and their basis values are read. |
| **Description** | **string** | Optional | A description of the Allocation Event. |
| **BasisValues** | [List&lt;AllocationMapBasisValue&gt;](AllocationMapBasisValue.md) | Optional | Optional basis values per investor record, used when the map&#39;s basis is not resolvable from stored data. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective datetime at which the event is created or replaced. Defaults to the earliest effective time on create and the current LUSID system datetime on replace. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventRequest(
    code: "...",  // required — The code of the Allocation Event. Together with the scope this uniquely identifies the event.
    allocationMapId: new ResourceId(...),  // required
    eventType: "...",  // required — The type of the event: CapitalCall, Distribution, FeeExpense or ValuationMove. Selects the basis rule from the map. Available values: CapitalCall, Distribution, FeeExpense, ValuationMove.
    amount: 0.0d,  // required — The total amount to be shared across the participants.
    currency: "...",  // required — The ISO 4217 code of the currency of the amount. The amount may not be finer than the currency&#39;s minor unit: two decimal places for most currencies, none for JPY, three for KWD and BHD. A code with no defined minor unit, such as XAU or XAG, is taken to have two decimal places.
    eventDate: DateTimeOffset.Now,  // required — The date of the event: the point at which the map, its participants and their basis values are read.
    description: "...",  // optional — A description of the Allocation Event.
    basisValues: new List<AllocationMapBasisValue>(),  // optional — Optional basis values per investor record, used when the map&#39;s basis is not resolvable from stored data.
    effectiveAt: DateTimeOffset.Now  // optional — The effective datetime at which the event is created or replaced. Defaults to the earliest effective time on create and the current LUSID system datetime on replace.
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


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

