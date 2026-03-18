# Finbourne.Sdk.Lusid.Model.CompositeBreakdownRequest

The request used in the GetCompositeBreakdown.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReturnIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The Scope and code of the returns. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CompositeMethod** | **string** | Optional | The method used to calculate the Portfolio performance: Equal/Asset. |
| **Period** | **string** | Optional | The type of the returns used to calculate the aggregation result: Daily/Monthly. |
| **HolidayCalendars** | **List&lt;string&gt;** | Optional | The holiday calendar(s) that should be used in determining the date schedule. Holiday calendar(s) are supplied by their codes, for example, &#39;CoppClark&#39;. Note that when the calendars are not available (e.g. when the user has insufficient permissions), a recipe setting will be used to determine whether the whole batch should then fail or whether the calendar not being available should simply be ignored. |
| **Currency** | **string** | Optional | Optional - either a string or a property. If provided, the results will be converted to the specified currency |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CompositeBreakdownRequest(
    returnIds: new List<ResourceId>(),  // optional — The Scope and code of the returns.
    recipeId: new ResourceId(...),  // optional
    compositeMethod: "...",  // optional — The method used to calculate the Portfolio performance: Equal/Asset.
    period: "...",  // optional — The type of the returns used to calculate the aggregation result: Daily/Monthly.
    holidayCalendars: ,  // optional — The holiday calendar(s) that should be used in determining the date schedule. Holiday calendar(s) are supplied by their codes, for example, &#39;CoppClark&#39;. Note that when the calendars are not available (e.g. when the user has insufficient permissions), a recipe setting will be used to determine whether the whole batch should then fail or whether the calendar not being available should simply be ignored.
    currency: "..."  // optional — Optional - either a string or a property. If provided, the results will be converted to the specified currency
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CompositeBreakdownRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `ReturnIds`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

