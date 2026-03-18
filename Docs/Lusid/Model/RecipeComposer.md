# Finbourne.Sdk.Lusid.Model.RecipeComposer

Recipe composer is an object used to dynamically compose Configuration Recipe from atomic operations.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope used when updating or inserting the Recipe Composer. |
| **Code** | **string** | Required | User given string name (code) to identify the recipe. |
| **Operations** | [List&lt;RecipeBlock&gt;](RecipeBlock.md) | Optional | Atomic operations used to compose a Configuration Recipe. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecipeComposer(
    scope: "...",  // required — The scope used when updating or inserting the Recipe Composer.
    code: "...",  // required — User given string name (code) to identify the recipe.
    operations: new List<RecipeBlock>()  // optional — Atomic operations used to compose a Configuration Recipe.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecipeComposer>(json);
```

- [RecipeBlock](RecipeBlock.md) — used in `Operations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

