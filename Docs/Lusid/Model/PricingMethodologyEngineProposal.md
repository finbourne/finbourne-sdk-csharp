# Finbourne.Sdk.Lusid.Model.PricingMethodologyEngineProposal

What the pricing methodology alone publishes for a share class, kept alongside any decision that replaces it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Swung** | **bool** | Required | Whether the methodology swings the price. |
| **SwingDirection** | **string** | Optional | Offer or Bid when the methodology swings the price. Absent when it does not. |
| **SpreadSource** | **string** | Optional | Where the methodology&#39;s spread came from: Stored or Market. Absent when it does not swing. |
| **SpreadBps** | **decimal?** | Optional | The stored spread the methodology applies, in basis points. Absent when it does not swing or swings to a market price. |
| **DealingPrice** | **decimal?** | Optional | The dealing price the methodology publishes. Absent when the class has no units in issue. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PricingMethodologyEngineProposal(
    swung: true,  // required — Whether the methodology swings the price.
    swingDirection: "...",  // optional — Offer or Bid when the methodology swings the price. Absent when it does not.
    spreadSource: "...",  // optional — Where the methodology&#39;s spread came from: Stored or Market. Absent when it does not swing.
    spreadBps: 0.0d,  // optional — The stored spread the methodology applies, in basis points. Absent when it does not swing or swings to a market price.
    dealingPrice: 0.0d  // optional — The dealing price the methodology publishes. Absent when the class has no units in issue.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PricingMethodologyEngineProposal>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

