# Finbourne.Sdk.Lusid.Model.SwingBaseline

The price a Single fund's dealing price starts from before any swing.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Source** | **string** | Required | The price the dealing price starts from: Mid, the share class unit price, or Bid or Offer, the share class price that the valuation recipe of each active NAV type publishes on that side. Available values: Mid, Bid, Offer. |
| **IncludeNdc** | **bool?** | Optional | Whether a Bid or Offer baseline reads the price including notional dealing costs, which needs the NAV type to have a notional dealing cost table. Required for a Bid or Offer baseline and must be omitted for a Mid baseline. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingBaseline(
    source: "...",  // required — The price the dealing price starts from: Mid, the share class unit price, or Bid or Offer, the share class price that the valuation recipe of each active NAV type publishes on that side. Available values: Mid, Bid, Offer.
    includeNdc: true  // optional — Whether a Bid or Offer baseline reads the price including notional dealing costs, which needs the NAV type to have a notional dealing cost table. Required for a Bid or Offer baseline and must be omitted for a Mid baseline.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingBaseline>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

