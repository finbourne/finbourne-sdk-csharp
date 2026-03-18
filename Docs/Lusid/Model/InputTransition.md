# Finbourne.Sdk.Lusid.Model.InputTransition

The input 'transition' within a corporate action, representing the singular input position
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UnitsFactor** | **decimal** | Required | The factor to scale units by |
| **CostFactor** | **decimal** | Required | The factor to scale cost by |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InputTransition(
    unitsFactor: 0.0d,  // required — The factor to scale units by
    costFactor: 0.0d  // required — The factor to scale cost by
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InputTransition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

