# Finbourne.Sdk.Lusid.Model.AppendFxForwardPipsCurveData

Used to append a new point to an FX curve defined using `FxForwardPipsCurveData`.
> **Inherits from:** [AppendMarketData](AppendMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Required | Date for which the forward rate applies. |
| **PipRate** | **decimal** | Required | Rate provided for the fx forward (price in FgnCcy per unit of DomCcy), expressed in pips. |
| **MarketDataType** | **string** | Required | The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData Default: `MarketDataTypeEnum.AppendFxForwardPipsCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AppendFxForwardPipsCurveData(
    date: DateTimeOffset.Now,  // required — Date for which the forward rate applies.
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
var instance = JsonConvert.DeserializeObject<AppendFxForwardPipsCurveData>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

