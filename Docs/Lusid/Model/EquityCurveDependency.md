# Finbourne.Sdk.Lusid.Model.EquityCurveDependency

For indicating a dependency on an EquityCurve.  E.g. When pricing an EquitySwap one may want to make predictions about the price of the underlying equity at future dates.  If so, that model would declare an EquityCurve dependency so that it could obtain predictions from the EquityCurve.
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketIdentifier** | **string** | Required | Type of the code identifying the corresponding equity, e.g. ISIN or CUSIP |
| **Code** | **string** | Required | The code identifying the corresponding equity, e.g. US0378331005 if the MarketIdentifier was set to ISIN |
| **CurveType** | **string** | Required | The curve type of the EquityCurve required. E.g. EquityCurveByPrices |
| **Date** | **DateTimeOffset** | Required | The effectiveDate of the entity that this is a dependency for.  Unless there is an obvious date this should be, like for a historic reset, then this is the valuation date. |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.EquityCurveDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquityCurveDependency(
    marketIdentifier: "...",  // required — Type of the code identifying the corresponding equity, e.g. ISIN or CUSIP
    code: "...",  // required — The code identifying the corresponding equity, e.g. US0378331005 if the MarketIdentifier was set to ISIN
    curveType: "...",  // required — The curve type of the EquityCurve required. E.g. EquityCurveByPrices
    date: DateTimeOffset.Now,  // required — The effectiveDate of the entity that this is a dependency for.  Unless there is an obvious date this should be, like for a historic reset, then this is the valuation date.
    dependencyType: "..."  // required — The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EquityCurveDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

