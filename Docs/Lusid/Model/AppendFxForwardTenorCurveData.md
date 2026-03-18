# Finbourne.Sdk.Lusid.Model.AppendFxForwardTenorCurveData

Used to append a new point to an FX curve defined using `FxForwardTenorCurveData`.
> **Inherits from:** [AppendMarketData](AppendMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tenor** | **string** | Required | Tenor for which the forward rate applies. |
| **Rate** | **decimal** | Required | Rate provided for the fx forward (price in FgnCcy per unit of DomCcy). |
| **MarketDataType** | **string** | Required | The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData Default: `MarketDataTypeEnum.AppendFxForwardTenorCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AppendFxForwardTenorCurveData(
    tenor: "...",  // required — Tenor for which the forward rate applies.
    rate: 0.0d,  // required — Rate provided for the fx forward (price in FgnCcy per unit of DomCcy).
    marketDataType: "..."  // required — The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AppendFxForwardTenorCurveData>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

