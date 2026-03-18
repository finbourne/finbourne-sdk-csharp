# Finbourne.Sdk.Lusid.Model.VendorDependency

For indicating a dependency on some opaque market data requested by an outside vendor
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency *(inherited)* |
| **VendorName** | **string** | Required | The name of the outside vendor |
| **VendorPath** | **List&lt;string&gt;** | Required | The specific dependency path |
| **Date** | **DateTimeOffset** | Required | The effectiveDate of the entity that this is a dependency for. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VendorDependency(
    vendorName: "...",  // required — The name of the outside vendor
    vendorPath: ,  // required — The specific dependency path
    date: DateTimeOffset.Now  // required — The effectiveDate of the entity that this is a dependency for.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VendorDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

