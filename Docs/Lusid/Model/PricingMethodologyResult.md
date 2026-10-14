# Finbourne.Sdk.Lusid.Model.PricingMethodologyResult

What a share class deals at under the fund's pricing methodology at a valuation point, the working behind it, and  the reporting prices the fund publishes for it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Dealing** | [SinglePriceDealing](SinglePriceDealing.md) | Optional | *No description available.* |
| **Audit** | [PricingMethodologyAudit](PricingMethodologyAudit.md) | Optional | *No description available.* |
| **DualDealing** | [DualPriceDealing](DualPriceDealing.md) | Optional | *No description available.* |
| **Reporting** | **Dictionary&lt;string, decimal?&gt;** | Optional | The Fund&#39;s reporting prices for the share class, keyed by label and rounded as the unit price is. A price is absent when the class has no units in issue or the valuation recipe does not publish it. Absent when the Fund has no reporting prices. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingMethodologyResult(
    dealing: new SinglePriceDealing(...),  // optional
    audit: new PricingMethodologyAudit(...),  // optional
    dualDealing: new DualPriceDealing(...),  // optional
    reporting:   // optional — The Fund&#39;s reporting prices for the share class, keyed by label and rounded as the unit price is. A price is absent when the class has no units in issue or the valuation recipe does not publish it. Absent when the Fund has no reporting prices.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingMethodologyResult>(json);
```


## Related Models

- [SinglePriceDealing](SinglePriceDealing.md)
- [PricingMethodologyAudit](PricingMethodologyAudit.md)
- [DualPriceDealing](DualPriceDealing.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

