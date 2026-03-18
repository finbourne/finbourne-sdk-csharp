# Finbourne.Sdk.Lusid.Model.InstrumentCapabilities

Instrument capabilities containing useful information about the instrument and the model. This includes  - features corresponding to the instrument i.e. Optionality:American, Other:InflationLinked  - supported addresses (if model provided) i.e. Valuation/Pv, Valuation/DirtyPriceKey, Valuation/Accrued  - economic dependencies (if model provided) i.e. Cash:USD, Fx:GBP.USD, Rates:GBP.GBPOIS
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentId** | **string** | Optional | The Lusid instrument id for the instrument e.g. &#39;LUID_00003D4X&#39;. |
| **Model** | **string** | Optional | The pricing model e.g. &#39;Discounting&#39;. |
| **Features** | **Dictionary&lt;string, string&gt;** | Optional | Features of the instrument describing its optionality, payoff type and more e.g. &#39;Instrument/Features/Exercise: American&#39;, &#39;Instrument/Features/Product: Option&#39; |
| **SupportedAddresses** | [List&lt;DescribedAddressKey&gt;](DescribedAddressKey.md) | Optional | Queryable addresses supported by the model, e.g. &#39;Valuation/Pv&#39;, &#39;Valuation/Accrued&#39;. |
| **EconomicDependencies** | [List&lt;EconomicDependency&gt;](EconomicDependency.md) | Optional | Economic dependencies for the model, e.g. &#39;Fx:GBP.USD&#39;, &#39;Cash:GBP&#39;, &#39;Rates:GBP.GBPOIS&#39;. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentCapabilities(
    instrumentId: "...",  // optional — The Lusid instrument id for the instrument e.g. &#39;LUID_00003D4X&#39;.
    model: "...",  // optional — The pricing model e.g. &#39;Discounting&#39;.
    features: ,  // optional — Features of the instrument describing its optionality, payoff type and more e.g. &#39;Instrument/Features/Exercise: American&#39;, &#39;Instrument/Features/Product: Option&#39;
    supportedAddresses: new List<DescribedAddressKey>(),  // optional — Queryable addresses supported by the model, e.g. &#39;Valuation/Pv&#39;, &#39;Valuation/Accrued&#39;.
    economicDependencies: new List<EconomicDependency>(),  // optional — Economic dependencies for the model, e.g. &#39;Fx:GBP.USD&#39;, &#39;Cash:GBP&#39;, &#39;Rates:GBP.GBPOIS&#39;.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentCapabilities>(json);
```

- [DescribedAddressKey](DescribedAddressKey.md) — used in `SupportedAddresses`
- [EconomicDependency](EconomicDependency.md) — used in `EconomicDependencies`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

