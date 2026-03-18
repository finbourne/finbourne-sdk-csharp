# Finbourne.Sdk.Lusid.Model.UpdateRelationalDatasetDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | A user-friendly display name for the relational dataset definition. |
| **Description** | **string** | Optional | A detailed description of the relational dataset definition and its purpose. |
| **ApplicableEntityTypes** | **List&lt;string&gt;** | Required | The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.). |
| **FieldSchema** | [List&lt;RelationalDatasetFieldDefinition&gt;](RelationalDatasetFieldDefinition.md) | Required | The schema defining the structure and data types of the relational dataset. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateRelationalDatasetDefinitionRequest(
    displayName: "...",  // required — A user-friendly display name for the relational dataset definition.
    description: "...",  // optional — A detailed description of the relational dataset definition and its purpose.
    applicableEntityTypes: ,  // required — The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.).
    fieldSchema: new List<RelationalDatasetFieldDefinition>()  // required — The schema defining the structure and data types of the relational dataset.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateRelationalDatasetDefinitionRequest>(json);
```

- [RelationalDatasetFieldDefinition](RelationalDatasetFieldDefinition.md) — used in `FieldSchema`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

