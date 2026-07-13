# Finbourne.Sdk.Lusid.Model.ValuationPointInstrument

An Instrument held at a Valuation Point, including its origin
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Instrument** | [Instrument](Instrument.md) | Optional | *No description available.* |
| **ValuationPointOrigin** | **string** | Optional | Designates if the instrument was originally part of the Valuation Point or if it was added as part of a Complex Close action. Available values: None, Original, Added, OriginalAndAdded. |
| **AddedOriginValuationPointCode** | **string** | Optional | The Valuation Point, only for an Instrument added as part of a Complex Close action. |
| **AddedOriginValuationPointVariantCode** | **string** | Optional | The Valuation Point variant, only for Instruments added as part of a Complex Close action. |
| **ValuationPointOriginSource** | **List&lt;string&gt;** | Optional | Collection of sources of Post Close Activities which added this instrument. Available values: Undefined, Manual, Auto. |
| **ValuationPointOriginType** | **List&lt;string&gt;** | Optional | Collection of types of Post Close Activities which added this instrument. Available values: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity, ComplexMarketDataActivity. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The requested instrument properties. These will be from the &#39;Instrument&#39; domain. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointInstrument(
    instrument: new Instrument(...),  // optional
    valuationPointOrigin: "...",  // optional — Designates if the instrument was originally part of the Valuation Point or if it was added as part of a Complex Close action. Available values: None, Original, Added, OriginalAndAdded.
    addedOriginValuationPointCode: "...",  // optional — The Valuation Point, only for an Instrument added as part of a Complex Close action.
    addedOriginValuationPointVariantCode: "...",  // optional — The Valuation Point variant, only for Instruments added as part of a Complex Close action.
    valuationPointOriginSource: ,  // optional — Collection of sources of Post Close Activities which added this instrument. Available values: Undefined, Manual, Auto.
    valuationPointOriginType: ,  // optional — Collection of types of Post Close Activities which added this instrument. Available values: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity, ComplexMarketDataActivity.
    properties: new Property(...)  // optional — The requested instrument properties. These will be from the &#39;Instrument&#39; domain.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointInstrument>(json);
```


## Related Models

- [Instrument](Instrument.md)
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

