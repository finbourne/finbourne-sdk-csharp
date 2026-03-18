# Finbourne.Sdk.Access.Model.PolicyTemplatedSelector

Templated selector for a policy template
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Application** | **string** | Required | The application that this selector definition applies to |
| **Tag** | **string** | Required | The type of policy that this selector definition applies to |
| **Selector** | [SelectorDefinition](SelectorDefinition.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicyTemplatedSelector(
    application: "...",  // required — The application that this selector definition applies to
    tag: "...",  // required — The type of policy that this selector definition applies to
    selector: new SelectorDefinition(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicyTemplatedSelector>(json);
```

- [SelectorDefinition](SelectorDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

