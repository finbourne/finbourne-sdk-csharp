# Finbourne.Sdk.Lusid.Model.UnitisationData

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SharesInIssue** | **decimal** | Required | The number of shares in issue at a valuation point. |
| **UnitPrice** | **decimal** | Required | The price of one unit of the share class at a valuation point. |
| **NetDealingUnits** | **decimal** | Required | The net dealing in units for the share class at a valuation point. This could be the sum of negative redemptions (in units) and positive subscriptions (in units). |
| **BidPrice** | **decimal?** | Optional | The price of one unit of the share class on the bid side at a valuation point: the class&#39;s NAV with the fund&#39;s holdings marked at their bid prices. Equal to the unit price when the fund is struck on the bid. Absent when a holding&#39;s bid could not be priced. |
| **OfferPrice** | **decimal?** | Optional | The price of one unit of the share class on the offer side at a valuation point: the class&#39;s NAV with the fund&#39;s holdings marked at their ask prices. Equal to the unit price when the fund is struck on the ask. Absent when a holding&#39;s ask could not be priced. |
| **BidPriceIncNdc** | **decimal?** | Optional | The bid price of one unit of the share class less the class&#39;s share of the notional dealing costs of selling the fund&#39;s holdings, at a valuation point. Absent when the NAV type has no notional dealing cost table. |
| **OfferPriceIncNdc** | **decimal?** | Optional | The offer price of one unit of the share class plus the class&#39;s share of the notional dealing costs of buying the fund&#39;s holdings, at a valuation point. Absent when the NAV type has no notional dealing cost table. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnitisationData(
    sharesInIssue: 0.0d,  // required — The number of shares in issue at a valuation point.
    unitPrice: 0.0d,  // required — The price of one unit of the share class at a valuation point.
    netDealingUnits: 0.0d,  // required — The net dealing in units for the share class at a valuation point. This could be the sum of negative redemptions (in units) and positive subscriptions (in units).
    bidPrice: 0.0d,  // optional — The price of one unit of the share class on the bid side at a valuation point: the class&#39;s NAV with the fund&#39;s holdings marked at their bid prices. Equal to the unit price when the fund is struck on the bid. Absent when a holding&#39;s bid could not be priced.
    offerPrice: 0.0d,  // optional — The price of one unit of the share class on the offer side at a valuation point: the class&#39;s NAV with the fund&#39;s holdings marked at their ask prices. Equal to the unit price when the fund is struck on the ask. Absent when a holding&#39;s ask could not be priced.
    bidPriceIncNdc: 0.0d,  // optional — The bid price of one unit of the share class less the class&#39;s share of the notional dealing costs of selling the fund&#39;s holdings, at a valuation point. Absent when the NAV type has no notional dealing cost table.
    offerPriceIncNdc: 0.0d  // optional — The offer price of one unit of the share class plus the class&#39;s share of the notional dealing costs of buying the fund&#39;s holdings, at a valuation point. Absent when the NAV type has no notional dealing cost table.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnitisationData>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

