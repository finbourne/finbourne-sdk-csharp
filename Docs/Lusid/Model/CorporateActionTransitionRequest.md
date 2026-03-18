# Finbourne.Sdk.Lusid.Model.CorporateActionTransitionRequest

A 'transition' within a corporate action, representing a set of output movements paired to a single input position
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InputTransition** | [CorporateActionTransitionComponentRequest](CorporateActionTransitionComponentRequest.md) | Optional | *No description available.* |
| **OutputTransitions** | [List&lt;CorporateActionTransitionComponentRequest&gt;](CorporateActionTransitionComponentRequest.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CorporateActionTransitionRequest(
    inputTransition: new CorporateActionTransitionComponentRequest(...),  // optional
    outputTransitions: new List<CorporateActionTransitionComponentRequest>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CorporateActionTransitionRequest>(json);
```


## Related Models

- [CorporateActionTransitionComponentRequest](CorporateActionTransitionComponentRequest.md)
- [CorporateActionTransitionComponentRequest](CorporateActionTransitionComponentRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

