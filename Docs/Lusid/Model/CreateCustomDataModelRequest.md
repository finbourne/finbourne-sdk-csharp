# Finbourne.Sdk.Lusid.Model.CreateCustomDataModelRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the Custom Data Model. |
| **Description** | **string** | Optional | A description for the Custom Data Model. |
| **ParentDataModel** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Conditions** | **string** | Optional | The conditions that the bound entity must meet to be valid. |
| **Properties** | [List&lt;CustomDataModelPropertySpecification&gt;](CustomDataModelPropertySpecification.md) | Optional | The properties that are required or allowed on the bound entity. |
| **IdentifierTypes** | [List&lt;CustomDataModelIdentifierTypeSpecification&gt;](CustomDataModelIdentifierTypeSpecification.md) | Optional | The identifier types that are required or allowed on the bound entity. |
| **AttributeAliases** | [List&lt;Alias&gt;](Alias.md) | Optional | The aliases for property keys, identifier types, and fields on the bound entity. |
| **RecommendedSortBy** | [List&lt;RecommendedSortBy&gt;](RecommendedSortBy.md) | Optional | The preferred default sorting instructions. |
| **SupplementalPropertyKeys** | **List&lt;string&gt;** | Optional | Additional property keys that should be decorated on the bound entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateCustomDataModelRequest(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the Custom Data Model.
    description: "...",  // optional — A description for the Custom Data Model.
    parentDataModel: new ResourceId(...),  // optional
    conditions: "...",  // optional — The conditions that the bound entity must meet to be valid.
    properties: new List<CustomDataModelPropertySpecification>(),  // optional — The properties that are required or allowed on the bound entity.
    identifierTypes: new List<CustomDataModelIdentifierTypeSpecification>(),  // optional — The identifier types that are required or allowed on the bound entity.
    attributeAliases: new List<Alias>(),  // optional — The aliases for property keys, identifier types, and fields on the bound entity.
    recommendedSortBy: new List<RecommendedSortBy>(),  // optional — The preferred default sorting instructions.
    supplementalPropertyKeys:   // optional — Additional property keys that should be decorated on the bound entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateCustomDataModelRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CustomDataModelPropertySpecification](CustomDataModelPropertySpecification.md) — used in `Properties`
- [CustomDataModelIdentifierTypeSpecification](CustomDataModelIdentifierTypeSpecification.md) — used in `IdentifierTypes`
- [Alias](Alias.md) — used in `AttributeAliases`
- [RecommendedSortBy](RecommendedSortBy.md) — used in `RecommendedSortBy`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

