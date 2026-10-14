# Finbourne.Sdk.Lusid.Model.DualPriceDealing

The bid and offer dealing prices a share class of a Dual fund publishes at a valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DealingBid** | **decimal?** | Optional | The price redemptions deal at, rounded as the share class unit price is. Absent when the class has no units in issue or the valuation did not price the side. |
| **DealingOffer** | **decimal?** | Optional | The price subscriptions deal at, rounded as the share class unit price is. Absent when the class has no units in issue or the valuation did not price the side. |
| **BidPerValuationSource** | **string** | Optional | The share class price the dealing bid was read or derived from: Bid when it is the bid read as published, Offer or Mid when it was derived from that price. Absent when nothing was dealt. |
| **OfferPerValuationSource** | **string** | Optional | The share class price the dealing offer was read or derived from: Offer when it is the offer read as published, Bid or Mid when it was derived from that price. Absent when nothing was dealt. |
| **BidSpreadBps** | **decimal?** | Optional | The spread, in basis points, the dealing bid was set below the price it was derived from by. Absent when the bid was read. |
| **OfferSpreadBps** | **decimal?** | Optional | The spread, in basis points, the dealing offer was set above the price it was derived from by. Absent when the offer was read. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DualPriceDealing(
    dealingBid: 0.0d,  // optional — The price redemptions deal at, rounded as the share class unit price is. Absent when the class has no units in issue or the valuation did not price the side.
    dealingOffer: 0.0d,  // optional — The price subscriptions deal at, rounded as the share class unit price is. Absent when the class has no units in issue or the valuation did not price the side.
    bidPerValuationSource: "...",  // optional — The share class price the dealing bid was read or derived from: Bid when it is the bid read as published, Offer or Mid when it was derived from that price. Absent when nothing was dealt.
    offerPerValuationSource: "...",  // optional — The share class price the dealing offer was read or derived from: Offer when it is the offer read as published, Bid or Mid when it was derived from that price. Absent when nothing was dealt.
    bidSpreadBps: 0.0d,  // optional — The spread, in basis points, the dealing bid was set below the price it was derived from by. Absent when the bid was read.
    offerSpreadBps: 0.0d  // optional — The spread, in basis points, the dealing offer was set above the price it was derived from by. Absent when the offer was read.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DualPriceDealing>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

