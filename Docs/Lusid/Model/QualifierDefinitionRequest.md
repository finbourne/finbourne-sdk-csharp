# Finbourne.Sdk.Lusid.Model.QualifierDefinitionRequest

A qualifier to declare against a single-value property definition.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key by which the qualifier is addressed, for example &#39;direction&#39;. Addressed in filters, sort orders and derivation formulae as Properties[{propertyKey}].Qualifiers[{qualifierKey}]. Validated under the same rules as a property code. |
| **DisplayName** | **string** | Required | The display name of the qualifier. |
| **Description** | **string** | Optional | Describes the qualifier. Optional; null where not supplied. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **IsRequired** | **bool?** | Optional | Whether a value for this qualifier must be supplied when a value of the property is written. Defaults to false, and is returned as a boolean rather than as null. Validated on write only, so setting it true does not retroactively invalidate values stored before the change. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QualifierDefinitionRequest(
    key: "...",  // required — The key by which the qualifier is addressed, for example &#39;direction&#39;. Addressed in filters, sort orders and derivation formulae as Properties[{propertyKey}].Qualifiers[{qualifierKey}]. Validated under the same rules as a property code.
    displayName: "...",  // required — The display name of the qualifier.
    description: "...",  // optional — Describes the qualifier. Optional; null where not supplied.
    dataTypeId: new ResourceId(...),  // required
    isRequired: true  // optional — Whether a value for this qualifier must be supplied when a value of the property is written. Defaults to false, and is returned as a boolean rather than as null. Validated on write only, so setting it true does not retroactively invalidate values stored before the change.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QualifierDefinitionRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

