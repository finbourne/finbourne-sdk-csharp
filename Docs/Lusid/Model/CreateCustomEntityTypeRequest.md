# Finbourne.Sdk.Lusid.Model.CreateCustomEntityTypeRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityTypeName** | **string** | Required | A name for the custom entity type. This will be prefixed with “~” and returned as “entityType”, which is the identifier for the custom entity type. |
| **DisplayName** | **string** | Required | A display label for the custom entity type. |
| **Description** | **string** | Required | A description for the custom entity type. |
| **FieldSchema** | [List&lt;CustomEntityFieldDefinition&gt;](CustomEntityFieldDefinition.md) | Required | The description of the fields on the custom entity type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateCustomEntityTypeRequest(
    entityTypeName: "...",  // required — A name for the custom entity type. This will be prefixed with “~” and returned as “entityType”, which is the identifier for the custom entity type.
    displayName: "...",  // required — A display label for the custom entity type.
    description: "...",  // required — A description for the custom entity type.
    fieldSchema: new List<CustomEntityFieldDefinition>()  // required — The description of the fields on the custom entity type.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateCustomEntityTypeRequest>(json);
```

- [CustomEntityFieldDefinition](CustomEntityFieldDefinition.md) — used in `FieldSchema`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

