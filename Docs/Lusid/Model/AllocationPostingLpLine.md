# Finbourne.Sdk.Lusid.Model.AllocationPostingLpLine

One instrument event a booking writes on an investor's commitment line.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The deterministic identifier of the posting: the booking reference, investor record, commitment line, component and side. |
| **Instrument** | **string** | Optional | The commitment-line instrument the event is written on. |
| **Portfolio** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Event** | **string** | Optional | The instrument event type written, for instance CapitalCallEvent. |
| **Amount** | **decimal** | Optional | The amount posted, in the event currency. |
| **Component** | **string** | Optional | The component of the event the posting carries. |
| **InvestorRecordId** | **string** | Optional | The investor record the posting is for. |
| **OriginMemberShortCode** | **string** | Optional | The member of the structure the component originates from, when it is not the map&#39;s own member. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPostingLpLine(
    id: "...",  // optional — The deterministic identifier of the posting: the booking reference, investor record, commitment line, component and side.
    instrument: "...",  // optional — The commitment-line instrument the event is written on.
    portfolio: new ResourceId(...),  // optional
    varEvent: "...",  // optional — The instrument event type written, for instance CapitalCallEvent.
    amount: 0.0d,  // optional — The amount posted, in the event currency.
    component: "...",  // optional — The component of the event the posting carries.
    investorRecordId: "...",  // optional — The investor record the posting is for.
    originMemberShortCode: "..."  // optional — The member of the structure the component originates from, when it is not the map&#39;s own member.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPostingLpLine>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

