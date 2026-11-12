# Finbourne.Sdk.Lusid.Model.EstimateValuationOutcome

Where a net cashflow leads the methodology: whether and which way it swings, the spread and tier it lands in, and the dealing price that results.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Swung** | **bool** | Required | Whether the methodology swings the price on this net cashflow. |
| **SwingDirection** | **string** | Optional | &#39;Bid&#39; or &#39;Offer&#39;, the side the price swings to. Absent when it does not swing. |
| **SpreadBps** | **decimal?** | Optional | The stored spread applied, in basis points. Absent when the price does not swing or the spread comes from the market. |
| **TierMatched** | [SwingSpreadTierBounds](SwingSpreadTierBounds.md) | Optional | *No description available.* |
| **DealingPrice** | **decimal?** | Optional | The dealing price the methodology publishes on this net cashflow. Absent when the baseline price is unavailable. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EstimateValuationOutcome(
    swung: true,  // required — Whether the methodology swings the price on this net cashflow.
    swingDirection: "...",  // optional — &#39;Bid&#39; or &#39;Offer&#39;, the side the price swings to. Absent when it does not swing.
    spreadBps: 0.0d,  // optional — The stored spread applied, in basis points. Absent when the price does not swing or the spread comes from the market.
    tierMatched: new SwingSpreadTierBounds(...),  // optional
    dealingPrice: 0.0d  // optional — The dealing price the methodology publishes on this net cashflow. Absent when the baseline price is unavailable.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EstimateValuationOutcome>(json);
```

- [SwingSpreadTierBounds](SwingSpreadTierBounds.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

