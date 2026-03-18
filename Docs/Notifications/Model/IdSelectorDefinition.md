# Finbourne.Sdk.Notifications.Model.IdSelectorDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifier** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **Actions** | [List&lt;ActionId&gt;](ActionId.md) | Required | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new IdSelectorDefinition(
    identifier: ,  // required
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
var instance = JsonConvert.DeserializeObject<IdSelectorDefinition>(json);
```

- [ActionId](ActionId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

