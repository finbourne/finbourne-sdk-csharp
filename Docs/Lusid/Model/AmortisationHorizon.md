# Finbourne.Sdk.Lusid.Model.AmortisationHorizon

The redemption a bond's cost is amortised towards, chosen per tax lot by whether the lot is held at a premium  (cost per unit above par) or a discount. Each value is one of Maturity, NextCall, NextPut or YieldToWorst and  defaults to Maturity. NextCall strikes a lot to its next call where the call price is below the lot's carrying  value, else to maturity until that call passes, so a discount lot is never struck to a call at or above par.  NextPut strikes to the next put at its price. YieldToWorst strikes to whichever call or the maturity gives the  lowest yield from the lot's cost.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Premium** | **string** | Optional | Available values: Maturity, NextCall, NextPut, YieldToWorst. |
| **Discount** | **string** | Optional | Available values: Maturity, NextCall, NextPut, YieldToWorst. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AmortisationHorizon(
    premium: "...",  // optional — Available values: Maturity, NextCall, NextPut, YieldToWorst.
    discount: "..."  // optional — Available values: Maturity, NextCall, NextPut, YieldToWorst.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AmortisationHorizon>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

