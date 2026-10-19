# Finbourne.Sdk.Lusid.Model.RecDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the rec definition. |
| **Description** | **string** | Optional | A description of the rec definition. |
| **SideNames** | [RecDefSideNames](RecDefSideNames.md) | Optional | *No description available.* |
| **Details** | [RecDefinitionDetails](RecDefinitionDetails.md) | Required | *No description available.* |
| **ReviewConfiguration** | [RecReviewConfiguration](RecReviewConfiguration.md) | Required | *No description available.* |
| **DatePolicy** | [RecDatePolicy](RecDatePolicy.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties in the RecDefinition domain. On update, a property with a null value is deleted and omitted properties are left unchanged. Filterable and sortable. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefinition(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the rec definition.
    description: "...",  // optional — A description of the rec definition.
    sideNames: new RecDefSideNames(...),  // optional
    details: new RecDefinitionDetails(...),  // required
    reviewConfiguration: new RecReviewConfiguration(...),  // required
    datePolicy: new RecDatePolicy(...),  // required
    properties: new PerpetualProperty(...),  // optional — Properties in the RecDefinition domain. On update, a property with a null value is deleted and omitted properties are left unchanged. Filterable and sortable.
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
var instance = JsonConvert.DeserializeObject<RecDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [RecDefSideNames](RecDefSideNames.md)
- [RecDefinitionDetails](RecDefinitionDetails.md)
- [RecReviewConfiguration](RecReviewConfiguration.md)
- [RecDatePolicy](RecDatePolicy.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

