# Finbourne.Sdk.Lusid.Model.AllocationEventRoundingResidual

The cents left over when one component of an Allocation Event was rounded to the currency's minor unit, and where they went.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Component** | **string** | Optional | The component the residual belongs to. |
| **Cents** | **int** | Optional | The number of minor units left over after each share was truncated to the currency. |
| **Amount** | **decimal** | Optional | The same, in the event currency. |
| **Method** | **string** | Optional | How the leftover was placed: LargestRemainder spreads it one minor unit at a time over the largest remainders; RoundingPartner gives all of it to the map&#39;s rounding partner line. Available values: LargestRemainder, RoundingPartner. |
| **TakenBy** | **List&lt;string&gt;** | Optional | The investor records that each took a minor unit, in the order they took it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventRoundingResidual(
    component: "...",  // optional — The component the residual belongs to.
    cents: 0,  // optional — The number of minor units left over after each share was truncated to the currency.
    amount: 0.0d,  // optional — The same, in the event currency.
    method: "...",  // optional — How the leftover was placed: LargestRemainder spreads it one minor unit at a time over the largest remainders; RoundingPartner gives all of it to the map&#39;s rounding partner line. Available values: LargestRemainder, RoundingPartner.
    takenBy:   // optional — The investor records that each took a minor unit, in the order they took it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventRoundingResidual>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

