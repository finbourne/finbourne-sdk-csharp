# Finbourne.Sdk.Lusid.Model.ReconciliationSideConfiguration

Specification for one side of a valuations/positions scheduled reconciliation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **EffectiveAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **Currency** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationSideConfiguration(
    recipeId: new ResourceId(...),  // optional
    effectiveAt: DateTimeOffset.Now,  // optional
    asAt: DateTimeOffset.Now,  // optional
    currency: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationSideConfiguration>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

