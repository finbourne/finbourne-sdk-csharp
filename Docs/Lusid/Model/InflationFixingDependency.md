# Finbourne.Sdk.Lusid.Model.InflationFixingDependency

For indicating a dependency upon an inflation fixing
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The Type of fixing (index, ratio or assumption) |
| **Code** | **string** | Required | The Code of the fixing, typically the index name |
| **Date** | **DateTimeOffset** | Required | The effectiveAt of the inflation fixing |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.InflationFixingDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationFixingDependency(
    type: "...",  // required — The Type of fixing (index, ratio or assumption)
    code: "...",  // required — The Code of the fixing, typically the index name
    date: DateTimeOffset.Now,  // required — The effectiveAt of the inflation fixing
    dependencyType: "..."  // required — The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationFixingDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

