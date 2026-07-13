# Finbourne.Sdk.Lusid.Model.ReturnsMetric

A metric requested from the aggregated-returns (TWR) endpoint. Supports only the  period `Return` (the grid granularity is set on the request via Period, not per metric);  `Alias` is the key the metric appears under in the response's metricsValue dictionary.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Available values: Return. |
| **Alias** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReturnsMetric(
    type: "...",  // optional — Available values: Return.
    alias: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReturnsMetric>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

