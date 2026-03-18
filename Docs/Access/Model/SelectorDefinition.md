# Finbourne.Sdk.Access.Model.SelectorDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MetadataSelectorDefinition** | [MetadataSelectorDefinition](MetadataSelectorDefinition.md) | Optional | *No description available.* |
| **IdSelectorDefinition** | [IdSelectorDefinition](IdSelectorDefinition.md) | Optional | *No description available.* |
| **MatchAllSelectorDefinition** | [MatchAllSelectorDefinition](MatchAllSelectorDefinition.md) | Optional | *No description available.* |
| **PolicySelectorDefinition** | [PolicySelectorDefinition](PolicySelectorDefinition.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new SelectorDefinition(
    metadataSelectorDefinition: new MetadataSelectorDefinition(...),  // optional
    idSelectorDefinition: new IdSelectorDefinition(...),  // optional
    matchAllSelectorDefinition: new MatchAllSelectorDefinition(...),  // optional
    policySelectorDefinition: new PolicySelectorDefinition(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SelectorDefinition>(json);
```


## Related Models

- [MetadataSelectorDefinition](MetadataSelectorDefinition.md)
- [IdSelectorDefinition](IdSelectorDefinition.md)
- [MatchAllSelectorDefinition](MatchAllSelectorDefinition.md)
- [PolicySelectorDefinition](PolicySelectorDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

