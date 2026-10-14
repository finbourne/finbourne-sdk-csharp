# Finbourne.Sdk.Lusid.Model.ReportingPrice

A share class price a fund publishes at each valuation point under a label of its own, alongside the dealing price.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Source** | **string** | Required | The share class price published: Mid, the unit price, or Bid, Offer, BidIncNdc or OfferIncNdc, as the valuation recipe of each active NAV type publishes it. Available values: Mid, Bid, Offer, BidIncNdc, OfferIncNdc, Creation, Cancellation. |
| **Label** | **string** | Required | The name the price is published under in the share class&#39;s reporting prices. Unique within the fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReportingPrice(
    source: "...",  // required — The share class price published: Mid, the unit price, or Bid, Offer, BidIncNdc or OfferIncNdc, as the valuation recipe of each active NAV type publishes it. Available values: Mid, Bid, Offer, BidIncNdc, OfferIncNdc, Creation, Cancellation.
    label: "..."  // required — The name the price is published under in the share class&#39;s reporting prices. Unique within the fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReportingPrice>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

