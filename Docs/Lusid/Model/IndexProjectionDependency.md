# Finbourne.Sdk.Lusid.Model.IndexProjectionDependency

Represents either a dependency on projections of an index.  E.g. If the interest leg of a swap is a FloatingLeg, then it will declare an IndexProjectionDependency upon pricing.  This is to indicate that pricing the floating leg requires predictions of future fixings of the index.
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Currency** | **string** | Required | The currency of the corresponding IndexConvention. E.g. this would be USD for a convention named USD.6M.LIBOR |
| **Tenor** | **string** | Required | The tenor of the corresponding IndexConvention. E.g. this would be \&quot;6M\&quot; for a convention named USD.6M.LIBOR |
| **IndexName** | **string** | Required | The IndexName of the corresponding IndexConvention. E.g. this would be \&quot;LIBOR\&quot; for a convention named USD.6M.LIBOR |
| **Date** | **DateTimeOffset** | Required | The effectiveDate of the entity that this is a dependency for.  Unless there is an obvious date this should be, like for a historic reset, then this is the valuation date. |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.IndexProjectionDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IndexProjectionDependency(
    currency: "...",  // required — The currency of the corresponding IndexConvention. E.g. this would be USD for a convention named USD.6M.LIBOR
    tenor: "...",  // required — The tenor of the corresponding IndexConvention. E.g. this would be \&quot;6M\&quot; for a convention named USD.6M.LIBOR
    indexName: "...",  // required — The IndexName of the corresponding IndexConvention. E.g. this would be \&quot;LIBOR\&quot; for a convention named USD.6M.LIBOR
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
var instance = JsonConvert.DeserializeObject<IndexProjectionDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

