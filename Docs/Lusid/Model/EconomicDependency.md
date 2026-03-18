# Finbourne.Sdk.Lusid.Model.EconomicDependency

Base class for representing economic dependencies.  Economic dependencies are a way of indicating how one concept depends upon another.  For example, when pricing an instrument with a particular model,  that model will declare that it has an EconomicDependency for each bit of market data  that it needs to complete the calculation.  Concretely, a pricing an FxForward will declare a dependency on the exchange rate between the two currencies  at the forward date.                Another example is when data is included in a data-structure only by reference.  Concretely, an object depending on a FlowConvention that is referenced only semantically via a FlowConventionName  will declare a FlowConventionDependency  so that the full data-structure of the referenced FlowConvention can be retrieved.                For deserialization purposes,  this class contains a discriminator EconomicDependencyType to indicate the derived type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EconomicDependency(
    dependencyType: "..."  // required — The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EconomicDependency>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

