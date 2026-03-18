# Finbourne.Sdk.Lusid.Model.FxVolDependency

Economic dependency required to price FX derivative products that contain optionality.  FX Vol surface is a grid of implied volatilities for an array of strikes and tenors,  derived from vanilla option prices in the market.
> **Inherits from:** [EconomicDependency](EconomicDependency.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DomesticCurrency** | **string** | Required | DomesticCurrency is the first currency in a currency pair quote e.g. eur-gbp, eur is the domestic currency. |
| **ForeignCurrency** | **string** | Required | ForeignCurrency is the second currency in a currency pair quote e.g. eur-gbp, gbp is the foreign currency. |
| **VolType** | **string** | Required | Volatility type e.g. \&quot;LN\&quot; and \&quot;N\&quot; for log-normal and normal volatility. |
| **Date** | **DateTimeOffset** | Required | The effectiveDate of the entity that this is a dependency for.  Unless there is an obvious date this should be, like for a historic reset, then this is the valuation date. |
| **DependencyType** | **string** | Required | The available values are: OpaqueDependency, CashDependency, DiscountingDependency, EquityCurveDependency, EquityVolDependency, FxDependency, FxForwardsDependency, FxVolDependency, IndexProjectionDependency, IrVolDependency, QuoteDependency, Vendor, CalendarDependency, InflationFixingDependency Default: `DependencyTypeEnum.FxVolDependency` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxVolDependency(
    domesticCurrency: "...",  // required — DomesticCurrency is the first currency in a currency pair quote e.g. eur-gbp, eur is the domestic currency.
    foreignCurrency: "...",  // required — ForeignCurrency is the second currency in a currency pair quote e.g. eur-gbp, gbp is the foreign currency.
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
var instance = JsonConvert.DeserializeObject<FxVolDependency>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

