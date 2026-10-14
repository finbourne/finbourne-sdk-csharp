# Finbourne.Sdk.Lusid.Model.UpdatePropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The display name of the property. |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **CustomEntityTypes** | **List&lt;string&gt;** | Optional | The custom entity types that properties relating to this property definition can be applied to. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. Available values: Text, Html. |
| **QualifierDefinitions** | [List&lt;QualifierDefinitionRequest&gt;](QualifierDefinitionRequest.md) | Optional | The qualifiers declared against this property definition. Omit this field, or supply it as null, to leave the declared qualifiers unchanged. Otherwise the supplied array replaces the stored array in full, so a qualifier omitted from it is no longer declared and can no longer be set, and an empty array clears every declaration. Stored qualifier values are retained in every case and become readable again if the same keys are re-declared with the same data types. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdatePropertyDefinitionRequest(
    displayName: "...",  // required — The display name of the property.
    propertyDescription: "...",  // optional — Describes the property
    customEntityTypes: ,  // optional — The custom entity types that properties relating to this property definition can be applied to.
    valueFormat: "...",  // optional — The format in which values for this property definition should be represented. Available values: Text, Html.
    qualifierDefinitions: new List<QualifierDefinitionRequest>()  // optional — The qualifiers declared against this property definition. Omit this field, or supply it as null, to leave the declared qualifiers unchanged. Otherwise the supplied array replaces the stored array in full, so a qualifier omitted from it is no longer declared and can no longer be set, and an empty array clears every declaration. Stored qualifier values are retained in every case and become readable again if the same keys are re-declared with the same data types.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePropertyDefinitionRequest>(json);
```

- [QualifierDefinitionRequest](QualifierDefinitionRequest.md) — used in `QualifierDefinitions`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

