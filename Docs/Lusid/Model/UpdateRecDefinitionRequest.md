# Finbourne.Sdk.Lusid.Model.UpdateRecDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the rec definition. |
| **Description** | **string** | Optional | A description of the rec definition. |
| **SideNames** | [RecDefSideNames](RecDefSideNames.md) | Optional | *No description available.* |
| **Details** | [RecDefinitionDetails](RecDefinitionDetails.md) | Required | *No description available.* |
| **ReviewConfiguration** | [RecReviewConfiguration](RecReviewConfiguration.md) | Optional | *No description available.* |
| **DatePolicy** | [RecDatePolicy](RecDatePolicy.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties in the RecDefinition domain. On update, a property with a null value is deleted and omitted properties are left unchanged. Filterable and sortable. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateRecDefinitionRequest(
    displayName: "...",  // required — The name of the rec definition.
    description: "...",  // optional — A description of the rec definition.
    sideNames: new RecDefSideNames(...),  // optional
    details: new RecDefinitionDetails(...),  // required
    reviewConfiguration: new RecReviewConfiguration(...),  // optional
    datePolicy: new RecDatePolicy(...),  // optional
    properties: new PerpetualProperty(...)  // optional — Properties in the RecDefinition domain. On update, a property with a null value is deleted and omitted properties are left unchanged. Filterable and sortable.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateRecDefinitionRequest>(json);
```

- [RecDefSideNames](RecDefSideNames.md)
- [RecDefinitionDetails](RecDefinitionDetails.md)
- [RecReviewConfiguration](RecReviewConfiguration.md)
- [RecDatePolicy](RecDatePolicy.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

