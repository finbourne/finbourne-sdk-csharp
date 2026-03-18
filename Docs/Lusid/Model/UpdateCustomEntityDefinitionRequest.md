# Finbourne.Sdk.Lusid.Model.UpdateCustomEntityDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | A display label for the custom entity type. |
| **Description** | **string** | Required | A description for the custom entity type. |
| **FieldSchema** | [List&lt;CustomEntityFieldDefinition&gt;](CustomEntityFieldDefinition.md) | Required | The description of the fields on the custom entity type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateCustomEntityDefinitionRequest(
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
var instance = JsonConvert.DeserializeObject<UpdateCustomEntityDefinitionRequest>(json);
```

- [CustomEntityFieldDefinition](CustomEntityFieldDefinition.md) — used in `FieldSchema`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

