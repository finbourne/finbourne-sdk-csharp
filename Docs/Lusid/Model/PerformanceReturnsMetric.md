# Finbourne.Sdk.Lusid.Model.PerformanceReturnsMetric

The request used in the AggregatedReturns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of the metric. Default to Return |
| **Window** | **string** | Optional | The given metric for the calculation i.e. 1Y, 1D. |
| **AllowPartial** | **bool** | Optional | Bool if the metric is allowed partial results. Default to false. |
| **Annualised** | **bool** | Optional | Bool if the metric is annualized. Default to false. |
| **WithFee** | **bool** | Optional | Bool if the metric should consider the fees when is calculated. Default to false. |
| **SeedAmount** | **string** | Optional | The given seed amount for the calculation of the indicative amount metrics. |
| **Alias** | **string** | Optional | The alias for the metric. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PerformanceReturnsMetric(
    type: "...",  // optional — The type of the metric. Default to Return
    window: "...",  // optional — The given metric for the calculation i.e. 1Y, 1D.
    allowPartial: true,  // optional — Bool if the metric is allowed partial results. Default to false.
    annualised: true,  // optional — Bool if the metric is annualized. Default to false.
    withFee: true,  // optional — Bool if the metric should consider the fees when is calculated. Default to false.
    seedAmount: "...",  // optional — The given seed amount for the calculation of the indicative amount metrics.
    alias: "..."  // optional — The alias for the metric.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PerformanceReturnsMetric>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

