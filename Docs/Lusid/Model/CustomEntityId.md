# Finbourne.Sdk.Lusid.Model.CustomEntityId

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdentifierScope** | **string** | Required | The scope the identifier resides in (the scope of the identifier property definition). |
| **IdentifierType** | **string** | Required | What the identifier represents (the code of the identifier property definition). |
| **IdentifierValue** | **string** | Required | The value of the identifier for this entity. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The effective datetime from which the identifier is valid. |
| **EffectiveUntil** | **DateTimeOffset?** | Optional | The effective datetime until which the identifier is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveFrom&#39; datetime of the identifier. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityId(
    identifierScope: "...",  // required — The scope the identifier resides in (the scope of the identifier property definition).
    identifierType: "...",  // required — What the identifier represents (the code of the identifier property definition).
    identifierValue: "...",  // required — The value of the identifier for this entity.
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime from which the identifier is valid.
    effectiveUntil: DateTimeOffset.Now  // optional — The effective datetime until which the identifier is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveFrom&#39; datetime of the identifier.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

