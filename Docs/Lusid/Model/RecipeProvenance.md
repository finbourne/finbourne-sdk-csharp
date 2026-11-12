# Finbourne.Sdk.Lusid.Model.RecipeProvenance

The recipe a fund valuation was priced with, and where it came from. Absent when the fund has no portfolios  at the effective date, as nothing is priced and no recipe is resolved.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Source** | **string** | Optional | Where the recipe came from. &#39;NavType&#39; when it is the recipe on the nominated NAV type&#39;s definition;  &#39;Request&#39; when the request named a recipeId that replaced it for pricing in that request only. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecipeProvenance(
    recipeId: new ResourceId(...),  // optional
    source: "..."  // optional — Where the recipe came from. &#39;NavType&#39; when it is the recipe on the nominated NAV type&#39;s definition;  &#39;Request&#39; when the request named a recipeId that replaced it for pricing in that request only.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecipeProvenance>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

