# Finbourne.Sdk.Insights.Model.ResourceListWithHistogramOfAccessEvaluationLog

ResourceList with additional aggregation data about the values.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Histogram** | [Histogram](Histogram.md) | Optional | *No description available.* |
| **Values** | [List&lt;AccessEvaluationLog&gt;](AccessEvaluationLog.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ResourceListWithHistogramOfAccessEvaluationLog(
    histogram: new Histogram(...),  // optional
    values: new List<AccessEvaluationLog>(),  // required
    href: "...",  // optional
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceListWithHistogramOfAccessEvaluationLog>(json);
```


## Related Models

- [Histogram](Histogram.md)
- [AccessEvaluationLog](AccessEvaluationLog.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

