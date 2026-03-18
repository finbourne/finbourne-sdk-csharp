# Finbourne.Sdk.Access.Model.AccessControlledResource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Application** | **string** | Optional | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Actions** | [List&lt;AccessControlledAction&gt;](AccessControlledAction.md) | Required | *No description available.* |
| **IdentifierParts** | [List&lt;IdentifierPartSchema&gt;](IdentifierPartSchema.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new AccessControlledResource(
    application: "...",  // optional
    name: "...",  // optional
    description: "...",  // required
    actions: new List<AccessControlledAction>(),  // required
    identifierParts: new List<IdentifierPartSchema>(),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccessControlledResource>(json);
```

- [AccessControlledAction](AccessControlledAction.md)
- [IdentifierPartSchema](IdentifierPartSchema.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

