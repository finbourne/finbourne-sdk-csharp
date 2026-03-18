# Finbourne.Sdk.Insights.Model.Histogram

A histogram showing an item's count in buckets of equal timespans.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Buckets** | [List&lt;Bucket&gt;](Bucket.md) | Optional | An ordered list of the histogram buckets. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new Histogram(
    buckets: new List<Bucket>()  // optional — An ordered list of the histogram buckets.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Histogram>(json);
```


## Related Models

- [Bucket](Bucket.md) — used in `Buckets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

