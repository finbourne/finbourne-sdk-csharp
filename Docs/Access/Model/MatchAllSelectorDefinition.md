# Finbourne.Sdk.Access.Model.MatchAllSelectorDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Actions** | [List&lt;ActionId&gt;](ActionId.md) | Required | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new MatchAllSelectorDefinition(
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
var instance = JsonConvert.DeserializeObject<MatchAllSelectorDefinition>(json);
```


## Related Models

- [ActionId](ActionId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

