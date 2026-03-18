# Finbourne.Sdk.Lusid.Model.UpdateDerivedPropertyDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The display name of the property. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PropertyDescription** | **string** | Optional | Describes the property |
| **DerivationFormula** | **string** | Required | The rule that defines how data is composed for a derived property. |
| **IsFilterable** | **bool** | Required | Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering. |
| **ValueFormat** | **string** | Optional | The format in which values for this property definition should be represented. |
| **CustomEntityType** | **string** | Optional | The custom entity type that this derived property definition can be applied to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateDerivedPropertyDefinitionRequest(
    displayName: "...",  // required — The display name of the property.
    dataTypeId: new ResourceId(...),  // required
    propertyDescription: "...",  // optional — Describes the property
    derivationFormula: "...",  // required — The rule that defines how data is composed for a derived property.
    isFilterable: true,  // required — Bool indicating whether the values of this property are fitlerable, this is true for all non-derived property defintions.  For a derived definition this must be set true to enable filtering.
    valueFormat: "...",  // optional — The format in which values for this property definition should be represented.
    customEntityType: "..."  // optional — The custom entity type that this derived property definition can be applied to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateDerivedPropertyDefinitionRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

