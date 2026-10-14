# Finbourne.Sdk.Lusid.Model.FundDetails

The details of a Fund.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Optional | The currency of the fund which is the same as the base currency of all the portfolios of the fund&#39;s Abor. |
| **PricingBasis** | **string** | Optional | The side of the quote the NAV type valued the fund on: Mid, Bid or Ask. Absent when the NAV type defers to the valuation recipe&#39;s own pricing basis. When the NAV type has a swing pricing rule this is the basis the rule applied. |
| **SwingPricing** | [SwingPricingDecision](SwingPricingDecision.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundDetails(
    currency: "...",  // optional — The currency of the fund which is the same as the base currency of all the portfolios of the fund&#39;s Abor.
    pricingBasis: "...",  // optional — The side of the quote the NAV type valued the fund on: Mid, Bid or Ask. Absent when the NAV type defers to the valuation recipe&#39;s own pricing basis. When the NAV type has a swing pricing rule this is the basis the rule applied.
    swingPricing: new SwingPricingDecision(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundDetails>(json);
```

- [SwingPricingDecision](SwingPricingDecision.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

