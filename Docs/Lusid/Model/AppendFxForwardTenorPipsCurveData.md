# Finbourne.Sdk.Lusid.Model.AppendFxForwardTenorPipsCurveData

Used to append a new point to an FX curve defined using `FxForwardTenorPipsCurveData`.
> **Inherits from:** [AppendMarketData](AppendMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tenor** | **string** | Required | Tenor for which the forward rate applies. |
| **PipRate** | **decimal** | Required | Rate provided for the fx forward (price in FgnCcy per unit of DomCcy), expressed in pips. |
| **MarketDataType** | **string** | Required | The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData Default: `MarketDataTypeEnum.AppendFxForwardTenorPipsCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AppendFxForwardTenorPipsCurveData(
    tenor: "...",  // required — Tenor for which the forward rate applies.
    pipRate: 0.0d,  // required — Rate provided for the fx forward (price in FgnCcy per unit of DomCcy), expressed in pips.
    marketDataType: "..."  // required — The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AppendFxForwardTenorPipsCurveData>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

