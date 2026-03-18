# Finbourne.Sdk.Lusid.Model.ComplexMarketDataId

An identifier that uniquely describes an item of complex market data such as an interest rate curve or volatility surface.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Provider** | **string** | Required | The platform or vendor that provided the complex market data, e.g. &#39;DataScope&#39;, &#39;LUSID&#39;, etc. |
| **PriceSource** | **string** | Optional | The source or originator of the complex market data, e.g. a bank or financial institution. |
| **Lineage** | **string** | Optional | This is obsolete. It is not used, it will not be stored, and has no effects.  If you wish to attach a Lineage to your ComplexMarketData,  you should provide it in the optional Lineage field in the ComplexMarketData class. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effectiveAt or cut label that this item of complex market data is/was updated/inserted with. |
| **MarketAsset** | **string** | Required | The name of the market entity that the document represents |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplexMarketDataId(
    provider: "...",  // required — The platform or vendor that provided the complex market data, e.g. &#39;DataScope&#39;, &#39;LUSID&#39;, etc.
    priceSource: "...",  // optional — The source or originator of the complex market data, e.g. a bank or financial institution.
    lineage: "...",  // optional — This is obsolete. It is not used, it will not be stored, and has no effects.  If you wish to attach a Lineage to your ComplexMarketData,  you should provide it in the optional Lineage field in the ComplexMarketData class.
    effectiveAt: new DateTimeOrCutLabel(...),  // optional — The effectiveAt or cut label that this item of complex market data is/was updated/inserted with.
    marketAsset: "..."  // required — The name of the market entity that the document represents
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplexMarketDataId>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

