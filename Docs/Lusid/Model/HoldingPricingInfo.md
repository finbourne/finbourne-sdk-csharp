# Finbourne.Sdk.Lusid.Model.HoldingPricingInfo

Enables price quotes to be created from Holding fields as either overrides or fallbacks to the Market Data  resolution process. For example, we may wish to price an instrument at Cost if Market Data resolution fails.  We may also wish to always price Bonds using the LastTradedPrice on the corresponding Holding.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FallbackField** | **string** | Optional | The default Holding field to fall back on if the Market Data resolution process fails to find a price quote. |
| **OverrideField** | **string** | Optional | The default Holding field to be used as an override for instrument price quotes. This cannot be specified  along with a FallbackField or any SpecificFallbacks, since we&#39;ll never attempt Market Data resolution  for price quotes if this field is populated. |
| **SpecificFallbacks** | [List&lt;SpecificHoldingPricingInfo&gt;](SpecificHoldingPricingInfo.md) | Optional | Allows a user to specify fallbacks using Holding fields for sources that match a particular DependencySourceFilter. |
| **SpecificOverrides** | [List&lt;SpecificHoldingPricingInfo&gt;](SpecificHoldingPricingInfo.md) | Optional | Allows a user to specify overrides using Holding fields for sources that match a particular DependencySourceFilter. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HoldingPricingInfo(
    fallbackField: "...",  // optional — The default Holding field to fall back on if the Market Data resolution process fails to find a price quote.
    overrideField: "...",  // optional — The default Holding field to be used as an override for instrument price quotes. This cannot be specified  along with a FallbackField or any SpecificFallbacks, since we&#39;ll never attempt Market Data resolution  for price quotes if this field is populated.
    specificFallbacks: new List<SpecificHoldingPricingInfo>(),  // optional — Allows a user to specify fallbacks using Holding fields for sources that match a particular DependencySourceFilter.
    specificOverrides: new List<SpecificHoldingPricingInfo>()  // optional — Allows a user to specify overrides using Holding fields for sources that match a particular DependencySourceFilter.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HoldingPricingInfo>(json);
```

- [SpecificHoldingPricingInfo](SpecificHoldingPricingInfo.md) — used in `SpecificFallbacks`
- [SpecificHoldingPricingInfo](SpecificHoldingPricingInfo.md) — used in `SpecificOverrides`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

