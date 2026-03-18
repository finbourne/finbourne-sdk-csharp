# Finbourne.Sdk.Lusid.Model.UpsertRecipeRequest

A recipe that is to be stored in the recipe structured data store.  Only one of these must be present.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ConfigurationRecipe** | [ConfigurationRecipe](ConfigurationRecipe.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertRecipeRequest(
    configurationRecipe: new ConfigurationRecipe(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertRecipeRequest>(json);
```


## Related Models

- [ConfigurationRecipe](ConfigurationRecipe.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

