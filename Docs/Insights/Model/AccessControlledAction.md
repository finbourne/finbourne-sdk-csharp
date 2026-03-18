# Finbourne.Sdk.Insights.Model.AccessControlledAction

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Description** | **string** | Required | *No description available.* |
| **Action** | [ActionId](ActionId.md) | Required | *No description available.* |
| **LimitedSet** | [List&lt;IdSelectorDefinition&gt;](IdSelectorDefinition.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AccessControlledAction(
    description: "...",  // required
    action: new ActionId(...),  // required
    limitedSet: new List<IdSelectorDefinition>(),  // optional
    links: new List<Link>()  // optional
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
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

