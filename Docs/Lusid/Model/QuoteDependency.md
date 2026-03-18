# Finbourne.Sdk.Lusid.Model.QuoteDependency

For indicating a dependency on the value of an asset at a point in time.  If the time is omitted, then the dependency is interpreted as the latest value with respect to anything observing it.  E.g. An EquitySwap will declare a dependency on the current price of the underlying equity.
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketIdentifier** | **string** | Required | Type of the code identifying the asset, e.g. ISIN or CUSIP |
| **Code** | **string** | Required | The code identifying the corresponding equity, e.g. US0378331005 if the MarketIdentifier was set to ISIN |
| **Date** | **DateTimeOffset** | Required | The effectiveAt of the quote for the identified entity. |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.QuoteDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QuoteDependency(
    marketIdentifier: "...",  // required — Type of the code identifying the asset, e.g. ISIN or CUSIP
    code: "...",  // required — The code identifying the corresponding equity, e.g. US0378331005 if the MarketIdentifier was set to ISIN
    date: DateTimeOffset.Now,  // required — The effectiveAt of the quote for the identified entity.
    dependencyType: "..."  // required — The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QuoteDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

