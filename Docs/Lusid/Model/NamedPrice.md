# Finbourne.Sdk.Lusid.Model.NamedPrice

One recipe-defined named price: the side of the market a PV is read from, and whether the  portfolio's notional dealing cost is added (buy side) or subtracted (sell side). The buy-side  cost is always computed from the offer-side market value and the sell-side cost from the  bid-side market value, whatever the base, so a mid base with a cost is well defined.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name a request uses, as Valuation/PV(NamedPrice&#x3D;name). Starts with a letter and contains  only letters and digits; at most 64 characters. |
| **Base** | **string** | Required | The side of the market the price starts from: one of \&quot;Bid\&quot;, \&quot;Mid\&quot; or \&quot;Offer\&quot;. \&quot;Bid\&quot; and \&quot;Offer\&quot;  read every instrument price rule on that side of the quote; \&quot;Mid\&quot; reads each rule with the quote  field it was written with, which is the recipe&#39;s ordinary valuation. Available values: Bid, Mid, Offer. |
| **Ndc** | **string** | Optional | The notional dealing cost applied to the base: one of \&quot;None\&quot; (default), \&quot;AddBuy\&quot; or  \&quot;SubtractSell\&quot;. Available values: None, AddBuy, SubtractSell. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NamedPrice(
    name: "...",  // required — The name a request uses, as Valuation/PV(NamedPrice&#x3D;name). Starts with a letter and contains  only letters and digits; at most 64 characters.
    varBase: "...",  // required — The side of the market the price starts from: one of \&quot;Bid\&quot;, \&quot;Mid\&quot; or \&quot;Offer\&quot;. \&quot;Bid\&quot; and \&quot;Offer\&quot;  read every instrument price rule on that side of the quote; \&quot;Mid\&quot; reads each rule with the quote  field it was written with, which is the recipe&#39;s ordinary valuation. Available values: Bid, Mid, Offer.
    ndc: "..."  // optional — The notional dealing cost applied to the base: one of \&quot;None\&quot; (default), \&quot;AddBuy\&quot; or  \&quot;SubtractSell\&quot;. Available values: None, AddBuy, SubtractSell.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NamedPrice>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

