# Finbourne.Sdk.Luminesce.Model.AccessControlledResource

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Application** | **string** | Optional | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Actions** | [List&lt;AccessControlledAction&gt;](AccessControlledAction.md) | Optional | *No description available.* |
| **IdentifierParts** | [List&lt;AccessControlledResourceIdentifierPartSchemaAttribute&gt;](AccessControlledResourceIdentifierPartSchemaAttribute.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new AccessControlledResource(
    application: "...",  // optional
    name: "...",  // optional
    description: "...",  // optional
    actions: new List<AccessControlledAction>(),  // optional
    identifierParts: new List<AccessControlledResourceIdentifierPartSchemaAttribute>()  // optional
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
- [AccessControlledResourceIdentifierPartSchemaAttribute](AccessControlledResourceIdentifierPartSchemaAttribute.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

