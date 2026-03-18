# Finbourne.Sdk.Lusid.Model.DependencySourceFilter

Encapsulates parts of a market data rule relating not to the nature of the market data requested, but rather the nature of the thing (instrument/model) that is requesting it.  In the first instance, this includes the instrument type, asset class, and the currency of the underlying instrument.  This can be used to differentiate requests for market data according to the source of the request. See MarketDataSpecificRule.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentType** | **string** | Optional | Specify that a rule should only apply if the market data is requested by an instrument of a given instrument type.  If null, then no filtering on instrument type is applied. |
| **AssetClass** | **string** | Optional | Specify that a rule should only apply if the market data is requested by an instrument of a given asset class.  If null, then no filtering on asset class is applied. |
| **DomCcy** | **string** | Optional | Specify that a rule should only apply if the market data is requested by an instrument with a given domestic currency.  If null, then no filtering on currency is applied. |
| **LongOrShortIndicator** | **string** | Optional | Specify that a rule should apply if the market data is requested by a model with a given long or short indicator.  If none, then no filtering on LongOrShortIndicator is applied. |
| **AddressKeyFilters** | [List&lt;AddressKeyFilter&gt;](AddressKeyFilter.md) | Optional | Specify that a rule should apply if the market data is requested by an instrument with features or properties  satisfying all the given address key filters. If an empty list is given, no additional filtering is done. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DependencySourceFilter(
    instrumentType: "...",  // optional — Specify that a rule should only apply if the market data is requested by an instrument of a given instrument type.  If null, then no filtering on instrument type is applied.
    assetClass: "...",  // optional — Specify that a rule should only apply if the market data is requested by an instrument of a given asset class.  If null, then no filtering on asset class is applied.
    domCcy: "...",  // optional — Specify that a rule should only apply if the market data is requested by an instrument with a given domestic currency.  If null, then no filtering on currency is applied.
    longOrShortIndicator: "...",  // optional — Specify that a rule should apply if the market data is requested by a model with a given long or short indicator.  If none, then no filtering on LongOrShortIndicator is applied.
    addressKeyFilters: new List<AddressKeyFilter>()  // optional — Specify that a rule should apply if the market data is requested by an instrument with features or properties  satisfying all the given address key filters. If an empty list is given, no additional filtering is done.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DependencySourceFilter>(json);
```

- [AddressKeyFilter](AddressKeyFilter.md) — used in `AddressKeyFilters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

