# Finbourne.Sdk.Lusid.Model.InflationConvexityOptions

Parameters of the Jarrow-Yildirim convexity correction applied to projected inflation index  values. Unlike most option blocks there is no defaulting here: nothing in the pricing chain  infers an index volatility, a nominal volatility or a correlation from market data, so an armed  correction is entirely the caller's stated view and every member must be supplied.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NominalIndexCorrelation** | **decimal?** | Optional | Correlation between the inflation index and the nominal short rate, in [-1, 1]. A positive  correlation makes the factor greater than one for a projection funded later than the curve&#39;s  own observation basis. |
| **IndexVolatility** | **decimal?** | Optional | Lognormal volatility of the inflation index, as a decimal (0.0095 is 0.95%). Must be  strictly positive - a zero volatility disarms the correction arithmetically, which is what  omitting the whole block already expresses. |
| **NominalVolatility** | **decimal?** | Optional | Volatility of the nominal short rate in the Hull-White dynamics the correction assumes, as a  decimal (0.008 is 80bp). Must be strictly positive. |
| **NominalMeanReversion** | **decimal?** | Optional | Mean reversion speed of the nominal short rate, per year. Must be strictly positive: the  closed form divides by it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationConvexityOptions(
    nominalIndexCorrelation: 0.0d,  // optional — Correlation between the inflation index and the nominal short rate, in [-1, 1]. A positive  correlation makes the factor greater than one for a projection funded later than the curve&#39;s  own observation basis.
    indexVolatility: 0.0d,  // optional — Lognormal volatility of the inflation index, as a decimal (0.0095 is 0.95%). Must be  strictly positive - a zero volatility disarms the correction arithmetically, which is what  omitting the whole block already expresses.
    nominalVolatility: 0.0d,  // optional — Volatility of the nominal short rate in the Hull-White dynamics the correction assumes, as a  decimal (0.008 is 80bp). Must be strictly positive.
    nominalMeanReversion: 0.0d  // optional — Mean reversion speed of the nominal short rate, per year. Must be strictly positive: the  closed form divides by it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationConvexityOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

