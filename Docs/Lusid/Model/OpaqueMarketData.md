# Finbourne.Sdk.Lusid.Model.OpaqueMarketData

A representation of an un-built piece of complex market data, to allow for passing through  to the vendor library for building.  The market data will usually be in some standard form such as XML or Json, representing a curve or surface.
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Document** | **string** | Required | The document as a string. |
| **Format** | **string** | Required | What format is the document stored in, e.g. Xml.  Supported string (enumeration) values are: [Unknown, Xml, Json, Csv]. |
| **Name** | **string** | Required | Internal name of document. This is not used for search, it is simply a designator that helps identify the document  and could be anything (filename, ftp address or similar) |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.OpaqueMarketData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OpaqueMarketData(
    document: "...",  // required — The document as a string.
    format: "...",  // required — What format is the document stored in, e.g. Xml.  Supported string (enumeration) values are: [Unknown, Xml, Json, Csv].
    name: "...",  // required — Internal name of document. This is not used for search, it is simply a designator that helps identify the document  and could be anything (filename, ftp address or similar)
    lineage: "...",  // optional — Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    varVersion: new ModelVersion(...),  // optional
    marketDataType: "..."  // required — The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OpaqueMarketData>(json);
```


- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

