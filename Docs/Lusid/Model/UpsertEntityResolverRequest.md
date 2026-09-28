# Finbourne.Sdk.Lusid.Model.UpsertEntityResolverRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The entity type that a specific resolution configuration is applicable to (e.g. Instrument). |
| **Description** | **string** | Optional | Describes what this specific identifier order is used for. |
| **IdentifierMatchingOrder** | [List&lt;IdentifierForResolution&gt;](IdentifierForResolution.md) | Required | Ordered collection of related identifier keys that are used to define which identifier takes priority in resolving an entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertEntityResolverRequest(
    entityType: "...",  // required — The entity type that a specific resolution configuration is applicable to (e.g. Instrument).
    description: "...",  // optional — Describes what this specific identifier order is used for.
    identifierMatchingOrder: new List<IdentifierForResolution>()  // required — Ordered collection of related identifier keys that are used to define which identifier takes priority in resolving an entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertEntityResolverRequest>(json);
```

- [IdentifierForResolution](IdentifierForResolution.md) — used in `IdentifierMatchingOrder`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

