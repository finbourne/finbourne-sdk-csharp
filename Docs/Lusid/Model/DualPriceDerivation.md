# Finbourne.Sdk.Lusid.Model.DualPriceDerivation

How a Dual fund derives its dealing prices from one real price by fixed spreads.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RealSide** | **string** | Required | The price read from the valuation: Bid or Offer, from which the other side is derived, or Mid, the share class unit price, from which both sides are derived, for a fund whose market data has no bid or offer. Available values: Bid, Offer, Mid. |
| **IncludeNdc** | **bool** | Required | Whether the real side is read including notional dealing costs, which needs the NAV type to have a notional dealing cost table. Must be false for Mid. |
| **BidSpreadBps** | **decimal?** | Optional | How far below the real price the bid is set, in basis points of the real price. Zero or more. Required when the bid is derived, for an Offer or Mid real side, and absent for a Bid one. |
| **OfferSpreadBps** | **decimal?** | Optional | How far above the real price the offer is set, in basis points of the real price. Zero or more. Required when the offer is derived, for a Bid or Mid real side, and absent for an Offer one. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DualPriceDerivation(
    realSide: "...",  // required — The price read from the valuation: Bid or Offer, from which the other side is derived, or Mid, the share class unit price, from which both sides are derived, for a fund whose market data has no bid or offer. Available values: Bid, Offer, Mid.
    includeNdc: true,  // required — Whether the real side is read including notional dealing costs, which needs the NAV type to have a notional dealing cost table. Must be false for Mid.
    bidSpreadBps: 0.0d,  // optional — How far below the real price the bid is set, in basis points of the real price. Zero or more. Required when the bid is derived, for an Offer or Mid real side, and absent for a Bid one.
    offerSpreadBps: 0.0d  // optional — How far above the real price the offer is set, in basis points of the real price. Zero or more. Required when the offer is derived, for a Bid or Mid real side, and absent for an Offer one.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DualPriceDerivation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

