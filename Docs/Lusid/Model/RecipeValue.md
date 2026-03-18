# Finbourne.Sdk.Lusid.Model.RecipeValue

Recipe value represents a data that is then used to perform an atomic operation which is then used in composition of Configuration Recipe.  This object either includes the data itself (in json form or as simple string) or is a reference where the data can be obtained from (from a Configuration Recipe say).  Only one field is to be populated.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsJson** | **string** | Optional | Field to allow providing a potentially complex json value. |
| **AsString** | **string** | Optional | For simple value, a single input value, note complex nested objects are not allowed here. |
| **FromRecipe** | [FromRecipe](FromRecipe.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecipeValue(
    asJson: "...",  // optional — Field to allow providing a potentially complex json value.
    asString: "...",  // optional — For simple value, a single input value, note complex nested objects are not allowed here.
    fromRecipe: new FromRecipe(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecipeValue>(json);
```

- [FromRecipe](FromRecipe.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

