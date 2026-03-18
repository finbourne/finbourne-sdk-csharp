# Finbourne.Sdk.Lusid.Model.AppendFxForwardCurveData

Used to append a new point to an FX curve defined using `FxForwardCurveData`.
> **Inherits from:** [AppendMarketData](AppendMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Required | Date for which the forward rate applies. |
| **Rate** | **decimal** | Required | Rate provided for the fx forward (price in FgnCcy per unit of DomCcy). |
| **MarketDataType** | **string** | Required | The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData Default: `MarketDataTypeEnum.AppendFxForwardCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AppendFxForwardCurveData(
    date: DateTimeOffset.Now,  // required — Date for which the forward rate applies.
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
var instance = JsonConvert.DeserializeObject<AppendFxForwardCurveData>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

