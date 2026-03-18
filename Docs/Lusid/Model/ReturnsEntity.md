# Finbourne.Sdk.Lusid.Model.ReturnsEntity

Returns entity, used for configuring the calculation of aggregated returns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **RecipeEntity** | **string** | Optional | Entity a recipe is retrieved from for use in the aggregated returns calculation. Either RecipeId or RecipeEntity must be specified. |
| **FeeHandling** | **string** | Optional | Configures how fees are handled in the aggregated returns calculation. |
| **FlowHandling** | **string** | Optional | Configures how flows are handled in the aggregated returns calculation. |
| **BusinessCalendar** | **string** | Optional | Calendar used in the aggregated returns calculation. |
| **HandleFlowDiscrepancy** | **string** | Optional | Configures handling for the case where net flows do not match the sum of tagged flows. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReturnsEntity(
    id: new ResourceId(...),  // required
    recipeId: new ResourceId(...),  // optional
    recipeEntity: "...",  // optional — Entity a recipe is retrieved from for use in the aggregated returns calculation. Either RecipeId or RecipeEntity must be specified.
    feeHandling: "...",  // optional — Configures how fees are handled in the aggregated returns calculation.
    flowHandling: "...",  // optional — Configures how flows are handled in the aggregated returns calculation.
    businessCalendar: "...",  // optional — Calendar used in the aggregated returns calculation.
    handleFlowDiscrepancy: "..."  // optional — Configures handling for the case where net flows do not match the sum of tagged flows.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReturnsEntity>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

