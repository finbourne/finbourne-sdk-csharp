# Finbourne.Sdk.Lusid.Model.SeriesConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassShortCode** | **string** | Required | *No description available.* |
| **SeriesLaunchPrice** | **decimal?** | Optional | *No description available.* |
| **DistributionSeriesSelection** | **string** | Optional | Available values: ProRataByNav, FIFO, SpecifiedSeries. |
| **DealLinkedSeries** | **bool?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SeriesConfiguration(
    shareClassShortCode: "...",  // required
    seriesLaunchPrice: 0.0d,  // optional
    distributionSeriesSelection: "...",  // optional — Available values: ProRataByNav, FIFO, SpecifiedSeries.
    dealLinkedSeries: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SeriesConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

