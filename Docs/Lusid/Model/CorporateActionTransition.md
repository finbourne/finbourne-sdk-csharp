# Finbourne.Sdk.Lusid.Model.CorporateActionTransition

A 'transition' within a corporate action, representing a set of output movements paired to a single input position
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InputTransition** | [CorporateActionTransitionComponent](CorporateActionTransitionComponent.md) | Optional | *No description available.* |
| **OutputTransitions** | [List&lt;CorporateActionTransitionComponent&gt;](CorporateActionTransitionComponent.md) | Optional | What will be generated relative to the input transition |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CorporateActionTransition(
    inputTransition: new CorporateActionTransitionComponent(...),  // optional
    outputTransitions: new List<CorporateActionTransitionComponent>()  // optional — What will be generated relative to the input transition
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CorporateActionTransition>(json);
```


## Related Models

- [CorporateActionTransitionComponent](CorporateActionTransitionComponent.md)
- [CorporateActionTransitionComponent](CorporateActionTransitionComponent.md) — used in `OutputTransitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

