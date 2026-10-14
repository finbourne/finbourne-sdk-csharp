# Finbourne.Sdk.Lusid.Model.SinglePriceDealing

The single dealing price a share class publishes at a valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DealingPrice** | **decimal?** | Optional | The price subscriptions and redemptions deal at, rounded as the share class unit price is. Absent when the class has no units in issue. |
| **Swung** | **bool** | Required | Whether the dealing price moved away from its baseline. |
| **SwingDirection** | **string** | Optional | Offer when a net inflow swung the price up, Bid when a net outflow swung it down. Absent when the price did not swing. |
| **SwingFrom** | **string** | Optional | The baseline the price swung away from. Absent when it did not swing. |
| **PerValuationSource** | **string** | Optional | Bid or Offer when the dealing price is that side&#39;s share class price read as published, from a Bid or Offer baseline or a Market swing. Absent when the price is the mid or a stored spread was applied to it. |
| **SpreadBps** | **decimal?** | Optional | The stored spread applied, in basis points. Absent when the price did not swing or swung to a market price. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SinglePriceDealing(
    dealingPrice: 0.0d,  // optional — The price subscriptions and redemptions deal at, rounded as the share class unit price is. Absent when the class has no units in issue.
    swung: true,  // required — Whether the dealing price moved away from its baseline.
    swingDirection: "...",  // optional — Offer when a net inflow swung the price up, Bid when a net outflow swung it down. Absent when the price did not swing.
    swingFrom: "...",  // optional — The baseline the price swung away from. Absent when it did not swing.
    perValuationSource: "...",  // optional — Bid or Offer when the dealing price is that side&#39;s share class price read as published, from a Bid or Offer baseline or a Market swing. Absent when the price is the mid or a stored spread was applied to it.
    spreadBps: 0.0d  // optional — The stored spread applied, in basis points. Absent when the price did not swing or swung to a market price.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SinglePriceDealing>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

