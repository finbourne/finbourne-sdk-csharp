# Finbourne.Sdk.Lusid.Model.InstrumentEventConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionTemplateScopes** | **List&lt;string&gt;** | Optional | *No description available.* |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventConfiguration(
    transactionTemplateScopes: ,  // optional
    recipeId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventConfiguration>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

