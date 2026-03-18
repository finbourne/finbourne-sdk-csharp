# Finbourne.Sdk.Luminesce.Model.AccessControlledAction

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Optional | *No description available.* |
| **Action** | [ActionId](ActionId.md) | Optional | *No description available.* |
| **LimitedSet** | [List&lt;IdSelectorDefinition&gt;](IdSelectorDefinition.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new AccessControlledAction(
    description: "...",  // optional
    action: new ActionId(...),  // optional
    limitedSet: new List<IdSelectorDefinition>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccessControlledAction>(json);
```

- [ActionId](ActionId.md)
- [IdSelectorDefinition](IdSelectorDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

