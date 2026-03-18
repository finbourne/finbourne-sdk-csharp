# Finbourne.Sdk.Lusid.Model.ListAggregationResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AggregationEffectiveAt** | **DateTimeOffset** | Optional | *No description available.* |
| **AggregationAsAt** | **DateTimeOffset** | Optional | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Data** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** | Optional | *No description available.* |
| **AggregationCurrency** | **string** | Optional | *No description available.* |
| **DataSchema** | [ResultDataSchema](ResultDataSchema.md) | Optional | *No description available.* |
| **AggregationFailures** | [List&lt;AggregationMeasureFailureDetail&gt;](AggregationMeasureFailureDetail.md) | Optional | *No description available.* |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ListAggregationResponse(
    aggregationEffectiveAt: DateTimeOffset.Now,  // optional
    aggregationAsAt: DateTimeOffset.Now,  // optional
    href: "...",  // optional
    data: ,  // optional
    aggregationCurrency: "...",  // optional
    dataSchema: new ResultDataSchema(...),  // optional
    aggregationFailures: new List<AggregationMeasureFailureDetail>(),  // optional
    recipeId: new ResourceId(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ListAggregationResponse>(json);
```

- [ResultDataSchema](ResultDataSchema.md)
- [AggregationMeasureFailureDetail](AggregationMeasureFailureDetail.md)
- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

