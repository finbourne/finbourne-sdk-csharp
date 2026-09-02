# Finbourne.Sdk.Lusid.Model.HullWhiteModelOptions

Model options for the Hull-White one-factor lattice pricer.
> **Inherits from:** [ModelOptions](ModelOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MeanReversion** | **decimal** | Optional | The mean reversion speed of the short rate. Must be strictly positive. Defaults to 0.03. |
| **Volatility** | **decimal** | Optional | The normal (absolute) volatility of the short rate, e.g. 0.008 for 80bp per year. Defaults to 0.008. |
| **LatticeSteps** | **int** | Optional | The number of uniform time steps in the lattice. More steps give a finer discretisation  of the short-rate process at greater computational cost. Defaults to 200. |
| **EffectiveRateBumpSize** | **decimal?** | Optional | The parallel curve shift, as an absolute rate, used for the central-difference effective  duration and convexity, e.g. 0.0001 for a 1bp bump. Must be strictly positive.  Defaults to 0.0025 (25bp, the market convention for option-adjusted risk) when not supplied. |
| **MeanReversionByCurrency** | **Dictionary&lt;string, decimal&gt;** | Optional | Per-currency mean-reversion overrides, keyed by ISO currency code.  A currency absent from this map uses MeanReversion. |
| **VolatilityByCurrency** | **Dictionary&lt;string, decimal&gt;** | Optional | Per-currency short-rate volatility overrides, keyed by ISO currency code.  A currency absent from this map uses Volatility. Short-rate volatility is a per-currency  quantity in practice, so a book spanning several currencies can calibrate each currency  separately instead of sharing a single global figure. |
| **ModelOptionsType** | **string** | Required | Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions. Default: `ModelOptionsTypeEnum.HullWhiteModelOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new HullWhiteModelOptions(
    meanReversion: 0.0d,  // optional — The mean reversion speed of the short rate. Must be strictly positive. Defaults to 0.03.
    volatility: 0.0d,  // optional — The normal (absolute) volatility of the short rate, e.g. 0.008 for 80bp per year. Defaults to 0.008.
    latticeSteps: 0,  // optional — The number of uniform time steps in the lattice. More steps give a finer discretisation  of the short-rate process at greater computational cost. Defaults to 200.
    effectiveRateBumpSize: 0.0d,  // optional — The parallel curve shift, as an absolute rate, used for the central-difference effective  duration and convexity, e.g. 0.0001 for a 1bp bump. Must be strictly positive.  Defaults to 0.0025 (25bp, the market convention for option-adjusted risk) when not supplied.
    meanReversionByCurrency: ,  // optional — Per-currency mean-reversion overrides, keyed by ISO currency code.  A currency absent from this map uses MeanReversion.
    volatilityByCurrency: ,  // optional — Per-currency short-rate volatility overrides, keyed by ISO currency code.  A currency absent from this map uses Volatility. Short-rate volatility is a per-currency  quantity in practice, so a book spanning several currencies can calibrate each currency  separately instead of sharing a single global figure.
    modelOptionsType: "..."  // required — Available values: Invalid, OpaqueModelOptions, EmptyModelOptions, IndexModelOptions, FxForwardModelOptions, FundingLegModelOptions, EquityModelOptions, CdsModelOptions, FlexibleLoanPricerOptions, HullWhiteModelOptions, BondLookupModelOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<HullWhiteModelOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

