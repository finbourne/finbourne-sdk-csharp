# Finbourne.Sdk.Lusid.Model.ApplicableEntity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The type of entity (e.g., Instrument, Portfolio) that this DataSeries applies to. |
| **EntityScope** | **string** | Optional | The scope of the entity. |
| **IdentifierScope** | **string** | Optional | The scope of the identifier used to uniquely identify the entity. |
| **IdentifierType** | **string** | Optional | The type of identifier (e.g., Figi, Isin) used to uniquely identify the entity. |
| **IdentifierValue** | **string** | Optional | The value of the identifier used to uniquely identify the entity. |
| **SubEntityId** | **string** | Optional | An optional sub-entity identifier, if applicable. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ApplicableEntity(
    entityType: "...",  // required — The type of entity (e.g., Instrument, Portfolio) that this DataSeries applies to.
    entityScope: "...",  // optional — The scope of the entity.
    identifierScope: "...",  // optional — The scope of the identifier used to uniquely identify the entity.
    identifierType: "...",  // optional — The type of identifier (e.g., Figi, Isin) used to uniquely identify the entity.
    identifierValue: "...",  // optional — The value of the identifier used to uniquely identify the entity.
    subEntityId: "..."  // optional — An optional sub-entity identifier, if applicable.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ApplicableEntity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

