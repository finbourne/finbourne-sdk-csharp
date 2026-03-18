# Finbourne.Sdk.Lusid.Model.UpsertRecipeComposerRequest

A recipe composer that is to be stored in the recipe composer data store or used for inline resolving.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecipeComposer** | [RecipeComposer](RecipeComposer.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertRecipeComposerRequest(
    recipeComposer: new RecipeComposer(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertRecipeComposerRequest>(json);
```


## Related Models

- [RecipeComposer](RecipeComposer.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

