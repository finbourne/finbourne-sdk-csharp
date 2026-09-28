# Finbourne.Sdk.Lusid.Model.QueryableKeysForMetricsResponse

The queryable key definition of each requested metric. Every requested metric appears in exactly one of  the two maps.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Metrics** | [Dictionary&lt;string, QueryableKey&gt;](QueryableKey.md) | Required | The definition of each metric that resolved, describing what a valuation returns for it and how to  present it. Keyed by the metric as it was requested, for example &#39;Valuation/PV&#39; or  &#39;ProfitAndLoss/Realised/Market(Window&#x3D;YTD)&#39;. Identical requested keys appear once; different  spellings of the same underlying key, such as a property&#39;s raw and wrapper forms, each appear. |
| **Failed** | **Dictionary&lt;string, string&gt;** | Required | Why each metric that did not resolve cannot be requested, keyed as for Metrics. Empty when every  metric resolved. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryableKeysForMetricsResponse(
    metrics: new QueryableKey(...),  // required — The definition of each metric that resolved, describing what a valuation returns for it and how to  present it. Keyed by the metric as it was requested, for example &#39;Valuation/PV&#39; or  &#39;ProfitAndLoss/Realised/Market(Window&#x3D;YTD)&#39;. Identical requested keys appear once; different  spellings of the same underlying key, such as a property&#39;s raw and wrapper forms, each appear.
    failed:   // required — Why each metric that did not resolve cannot be requested, keyed as for Metrics. Empty when every  metric resolved.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryableKeysForMetricsResponse>(json);
```


## Related Models

- [QueryableKey](QueryableKey.md) — used in `Metrics`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

