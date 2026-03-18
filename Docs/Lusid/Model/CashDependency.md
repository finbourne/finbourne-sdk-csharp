# Finbourne.Sdk.Lusid.Model.CashDependency

For indicating a dependency upon a currency.  E.g. A Bond will declare a CashDependency for its domestic currency.
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Required | The Currency that is depended upon. |
| **Date** | **DateTimeOffset** | Required | The effectiveDate of the entity that this is a dependency for.  Unless there is an obvious date this should be, like for a historic reset, then this is the valuation date. |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.CashDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashDependency(
    currency: "...",  // required — The Currency that is depended upon.
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
var instance = JsonConvert.DeserializeObject<CashDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

