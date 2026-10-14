# Finbourne.Sdk.Lusid.Model.AllocationPostingRollUp

One roll-up a booking writes on a vehicle's line on the register above it, summing the lines beneath.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The deterministic identifier of the posting: the booking reference, investor record, commitment line, component and side. |
| **Line** | **string** | Optional | The roll-up line, rendered as the held vehicle and the register above it. |
| **Portfolio** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Amount** | **decimal** | Optional | The amount posted, in the event currency. |
| **Component** | **string** | Optional | The component of the event the posting carries. |
| **SumOf** | **List&lt;string&gt;** | Optional | The identifiers of the postings beneath that the roll-up sums. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPostingRollUp(
    id: "...",  // optional — The deterministic identifier of the posting: the booking reference, investor record, commitment line, component and side.
    line: "...",  // optional — The roll-up line, rendered as the held vehicle and the register above it.
    portfolio: new ResourceId(...),  // optional
    amount: 0.0d,  // optional — The amount posted, in the event currency.
    component: "...",  // optional — The component of the event the posting carries.
    sumOf:   // optional — The identifiers of the postings beneath that the roll-up sums.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPostingRollUp>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

