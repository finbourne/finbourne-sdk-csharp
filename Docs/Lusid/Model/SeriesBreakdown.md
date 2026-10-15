# Finbourne.Sdk.Lusid.Model.SeriesBreakdown

The valuation of one series within a share class at a valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SeriesIdentifier** | **string** | Required | The identifier of the series within its share class. |
| **Units** | **decimal** | Required | The units in issue in the series at the valuation point. |
| **Nav** | **decimal** | Required | The series&#39; share of the share class NAV, in the fund currency. |
| **NavPerUnit** | **decimal** | Required | The series NAV per unit in the share class currency, rounded as the share class unit price is. |
| **CapitalRatio** | **decimal** | Required | The series&#39; opening NAV as a proportion of the share class&#39;s opening NAV. Zero for a series with no units; sums to 1 across the series that hold units. |
| **Pnl** | **decimal** | Required | The P&amp;L apportioned to the series in the period: its NAV less its opening NAV. |
| **PreviousNav** | **decimal** | Required | The series NAV at the previous valuation point, in the fund currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SeriesBreakdown(
    seriesIdentifier: "...",  // required — The identifier of the series within its share class.
    units: 0.0d,  // required — The units in issue in the series at the valuation point.
    nav: 0.0d,  // required — The series&#39; share of the share class NAV, in the fund currency.
    navPerUnit: 0.0d,  // required — The series NAV per unit in the share class currency, rounded as the share class unit price is.
    capitalRatio: 0.0d,  // required — The series&#39; opening NAV as a proportion of the share class&#39;s opening NAV. Zero for a series with no units; sums to 1 across the series that hold units.
    pnl: 0.0d,  // required — The P&amp;L apportioned to the series in the period: its NAV less its opening NAV.
    previousNav: 0.0d  // required — The series NAV at the previous valuation point, in the fund currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SeriesBreakdown>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

