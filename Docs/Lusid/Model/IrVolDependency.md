# Finbourne.Sdk.Lusid.Model.IrVolDependency

Economic dependency required to price interest rate products that contain optionality, for example swaptions.  For example, can indicate a dependency on an IrVolCubeData.
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Required | The domestic currency of the instrument declaring this dependency. |
| **VolType** | **string** | Required | Volatility type e.g. \&quot;LN\&quot; and \&quot;N\&quot; for log-normal and normal volatility. |
| **Date** | **DateTimeOffset** | Required | The effectiveDate of the entity that this is a dependency for.  Unless there is an obvious date this should be, like for a historic reset, then this is the valuation date. |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.IrVolDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IrVolDependency(
    currency: "...",  // required — The domestic currency of the instrument declaring this dependency.
    volType: "...",  // required — Volatility type e.g. \&quot;LN\&quot; and \&quot;N\&quot; for log-normal and normal volatility.
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
var instance = JsonConvert.DeserializeObject<IrVolDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

