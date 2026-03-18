# Finbourne.Sdk.Lusid.Model.AggregatedReturnsDispersionRequest

The request used in the AggregatedReturnsDispersionMetric.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ToEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The end date for when the you want the dispersion to be calculated. |
| **YearsCount** | **int** | Optional | For how many years to calculate the dispersion. Default to 10. |
| **ReturnIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The Scope and code of the returns. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CompositeMethod** | **string** | Optional | The method used to calculate the Portfolio performance: Equal/Asset. |
| **AlternativeInceptionDate** | **string** | Optional | Optional - either a date, or the key for a portfolio property containing a date. If provided, the given date will override the inception date for this request. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedReturnsDispersionRequest(
    toEffectiveAt: new DateTimeOrCutLabel(...),  // optional — The end date for when the you want the dispersion to be calculated.
    yearsCount: 0,  // optional — For how many years to calculate the dispersion. Default to 10.
    returnIds: new List<ResourceId>(),  // optional — The Scope and code of the returns.
    recipeId: new ResourceId(...),  // optional
    compositeMethod: "...",  // optional — The method used to calculate the Portfolio performance: Equal/Asset.
    alternativeInceptionDate: "..."  // optional — Optional - either a date, or the key for a portfolio property containing a date. If provided, the given date will override the inception date for this request.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregatedReturnsDispersionRequest>(json);
```


## Related Models

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `ToEffectiveAt`
- [ResourceId](ResourceId.md) — used in `ReturnIds`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

