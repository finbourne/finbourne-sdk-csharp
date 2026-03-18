# Finbourne.Sdk.Lusid.Model.GroupReconciliationDefinitionRecipeIds

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Right** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDefinitionRecipeIds(
    left: new ResourceId(...),  // required
    right: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDefinitionRecipeIds>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

