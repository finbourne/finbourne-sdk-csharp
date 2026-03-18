# Finbourne.Sdk.Lusid.Model.UpdateIdentifierDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HierarchyLevel** | **string** | Optional | Optional metadata associated with the identifier definition. |
| **DisplayName** | **string** | Optional | A display name for the identifier. E.g. Figi. |
| **Description** | **string** | Optional | An optional description for the identifier. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the identifier definition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateIdentifierDefinitionRequest(
    hierarchyLevel: "...",  // optional — Optional metadata associated with the identifier definition.
    displayName: "...",  // optional — A display name for the identifier. E.g. Figi.
    description: "...",  // optional — An optional description for the identifier.
    properties: new Property(...)  // optional — A set of properties for the identifier definition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateIdentifierDefinitionRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

