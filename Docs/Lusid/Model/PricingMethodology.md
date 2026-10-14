# Finbourne.Sdk.Lusid.Model.PricingMethodology

How a fund prices its share classes for dealing. A Single fund deals at one price per class, which starts at a  baseline and may swing with the fund's net cashflow. A Dual fund deals at a bid and an offer per class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OutputShape** | **string** | Required | How many dealing prices each share class publishes: Single, one price that subscriptions and redemptions both deal at, or Dual, a bid that redemptions deal at and an offer that subscriptions deal at. Available values: Single, Dual. |
| **SwingPolicy** | [SwingPolicy](SwingPolicy.md) | Optional | *No description available.* |
| **PriceLabels** | **string** | Optional | What a Dual fund&#39;s two prices are. BidOffer is the only label available: the bid and the offer, including notional dealing costs, that the valuation recipe of each active NAV type publishes. Required for a Dual fund and must be omitted for a Single fund. Available values: BidOffer, CreationCancellation. |
| **Derivation** | [DualPriceDerivation](DualPriceDerivation.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingMethodology(
    outputShape: "...",  // required — How many dealing prices each share class publishes: Single, one price that subscriptions and redemptions both deal at, or Dual, a bid that redemptions deal at and an offer that subscriptions deal at. Available values: Single, Dual.
    swingPolicy: new SwingPolicy(...),  // optional
    priceLabels: "...",  // optional — What a Dual fund&#39;s two prices are. BidOffer is the only label available: the bid and the offer, including notional dealing costs, that the valuation recipe of each active NAV type publishes. Required for a Dual fund and must be omitted for a Single fund. Available values: BidOffer, CreationCancellation.
    derivation: new DualPriceDerivation(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingMethodology>(json);
```

- [SwingPolicy](SwingPolicy.md)
- [DualPriceDerivation](DualPriceDerivation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

