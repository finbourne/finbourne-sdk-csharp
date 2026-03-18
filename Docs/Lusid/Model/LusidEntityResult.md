# Finbourne.Sdk.Lusid.Model.LusidEntityResult

Represents LUSID entity details for a data quality check result
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Optional | The as-at timestamp for the entity |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective-at timestamp for the entity |
| **EntityType** | **string** | Optional | The type of the LUSID entity |
| **Scope** | **string** | Optional | The scope of the entity |
| **IdentifierKey** | **string** | Optional | The identifier key for the entity |
| **IdentifierValue** | **string** | Optional | The identifier value for the entity |
| **EntityUniqueId** | **string** | Optional | The unique identifier for the entity |
| **DisplayName** | **string** | Optional | The display name of the entity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LusidEntityResult(
    asAt: DateTimeOffset.Now,  // optional — The as-at timestamp for the entity
    effectiveAt: DateTimeOffset.Now,  // optional — The effective-at timestamp for the entity
    entityType: "...",  // optional — The type of the LUSID entity
    scope: "...",  // optional — The scope of the entity
    identifierKey: "...",  // optional — The identifier key for the entity
    identifierValue: "...",  // optional — The identifier value for the entity
    entityUniqueId: "...",  // optional — The unique identifier for the entity
    displayName: "..."  // optional — The display name of the entity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidEntityResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

