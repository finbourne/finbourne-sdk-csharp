# Finbourne.Sdk.Lusid.Model.PricingMethodologyOverrideRequest

A fund manager's choice of basis for a valuation point's dealing price, in place of the pricing methodology's  decision. The spread still comes from the methodology.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Decision** | **string** | Required | The basis the dealing price is published on: Mid, Bid or Offer. Under a Stored spread source the spread for Bid or Offer is the stored tier the net cashflow matches in that direction, or that direction&#39;s first tier when the flow is below every tier. Under a Market spread source Bid or Offer reads that side&#39;s price including notional dealing costs, which every active NAV type&#39;s valuation recipe must publish. Available values: Mid, Bid, Offer. |
| **Reason** | **string** | Required | Why the fund manager overrode the methodology&#39;s decision. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingMethodologyOverrideRequest(
    decision: "...",  // required — The basis the dealing price is published on: Mid, Bid or Offer. Under a Stored spread source the spread for Bid or Offer is the stored tier the net cashflow matches in that direction, or that direction&#39;s first tier when the flow is below every tier. Under a Market spread source Bid or Offer reads that side&#39;s price including notional dealing costs, which every active NAV type&#39;s valuation recipe must publish. Available values: Mid, Bid, Offer.
    reason: "..."  // required — Why the fund manager overrode the methodology&#39;s decision.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingMethodologyOverrideRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

