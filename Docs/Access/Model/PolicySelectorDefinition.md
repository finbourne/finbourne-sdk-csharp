# Finbourne.Sdk.Access.Model.PolicySelectorDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdentityRestriction** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **RestrictionSelectors** | [List&lt;SelectorDefinition&gt;](SelectorDefinition.md) | Optional | *No description available.* |
| **Actions** | [List&lt;ActionId&gt;](ActionId.md) | Required | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new PolicySelectorDefinition(
    identityRestriction: ,  // optional
    restrictionSelectors: new List<SelectorDefinition>(),  // optional
    actions: new List<ActionId>(),  // required
    name: "...",  // optional
    description: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PolicySelectorDefinition>(json);
```

- [SelectorDefinition](SelectorDefinition.md)
- [ActionId](ActionId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

