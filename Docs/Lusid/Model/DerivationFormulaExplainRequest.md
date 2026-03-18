# Finbourne.Sdk.Lusid.Model.DerivationFormulaExplainRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The type of the entity for which the derived property or partial formula is to be resolved against. |
| **Scope** | **string** | Optional | (Optional) The scope that entity exists in. If no scope is provided, the default scope for the entity type will be used. |
| **Code** | **string** | Optional | (Optional) The code of the entity, to be provided for entities that support scope/code retrieval. If no code or identifier is provided, the logical evaluation tree without resolved values is returned. |
| **SubentityId** | **string** | Optional | (Optional) The id of the sub-entity to explain the derived property for. This must be provided along with the scope/code of the parent entity. |
| **Identifier** | **Dictionary&lt;string, string&gt;** | Optional | (Optional). An identifier key/value pair that uniquely identifies the entity to explain the derived property for. This can be either an instrument identifier, or an identifier property. If no code or identifier is provided, the logical evaluation tree without resolved values is returned. |
| **PropertyKey** | **string** | Optional | (Optional) The key of the derived property to get an explanation for. This takes the format {domain}/{scope}/{code}. One of either property key or partial formula must be provided. |
| **PartialFormula** | **string** | Optional | (Optional) A partial derivation formula to get an explanation for. Can be provided in lieu of a property key. One of either property key or partial formula must be provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DerivationFormulaExplainRequest(
    entityType: "...",  // required — The type of the entity for which the derived property or partial formula is to be resolved against.
    scope: "...",  // optional — (Optional) The scope that entity exists in. If no scope is provided, the default scope for the entity type will be used.
    code: "...",  // optional — (Optional) The code of the entity, to be provided for entities that support scope/code retrieval. If no code or identifier is provided, the logical evaluation tree without resolved values is returned.
    subentityId: "...",  // optional — (Optional) The id of the sub-entity to explain the derived property for. This must be provided along with the scope/code of the parent entity.
    identifier: ,  // optional — (Optional). An identifier key/value pair that uniquely identifies the entity to explain the derived property for. This can be either an instrument identifier, or an identifier property. If no code or identifier is provided, the logical evaluation tree without resolved values is returned.
    propertyKey: "...",  // optional — (Optional) The key of the derived property to get an explanation for. This takes the format {domain}/{scope}/{code}. One of either property key or partial formula must be provided.
    partialFormula: "..."  // optional — (Optional) A partial derivation formula to get an explanation for. Can be provided in lieu of a property key. One of either property key or partial formula must be provided.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DerivationFormulaExplainRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

