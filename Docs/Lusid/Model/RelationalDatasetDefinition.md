# Finbourne.Sdk.Lusid.Model.RelationalDatasetDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | A user-friendly display name for the relational dataset definition. |
| **Description** | **string** | Optional | A detailed description of the relational dataset definition and its purpose. |
| **ApplicableEntityTypes** | **List&lt;string&gt;** | Required | The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.). |
| **FieldSchema** | [List&lt;RelationalDatasetFieldDefinition&gt;](RelationalDatasetFieldDefinition.md) | Required | The schema defining the structure and data types of the relational dataset. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationalDatasetDefinition(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — A user-friendly display name for the relational dataset definition.
    description: "...",  // optional — A detailed description of the relational dataset definition and its purpose.
    applicableEntityTypes: ,  // required — The types of entities this relational dataset definition can be applied to (e.g. Instrument, Portfolio, etc.).
    fieldSchema: new List<RelationalDatasetFieldDefinition>(),  // required — The schema defining the structure and data types of the relational dataset.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationalDatasetDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [RelationalDatasetFieldDefinition](RelationalDatasetFieldDefinition.md) — used in `FieldSchema`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

