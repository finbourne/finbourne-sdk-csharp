# Finbourne.Sdk.Lusid.Model.RecipeBlock

An atomic operation used in Recipe composer to compose a Configuration Recipe
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | [RecipeValue](RecipeValue.md) | Optional | *No description available.* |
| **Path** | **string** | Optional | Path of the Value that the operation is to be performed on. |
| **Op** | **string** | Optional | Operation to be performed on the part of the value. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecipeBlock(
    value: new RecipeValue(...),  // optional
    path: "...",  // optional — Path of the Value that the operation is to be performed on.
    op: "..."  // optional — Operation to be performed on the part of the value.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecipeBlock>(json);
```


## Related Models

- [RecipeValue](RecipeValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

