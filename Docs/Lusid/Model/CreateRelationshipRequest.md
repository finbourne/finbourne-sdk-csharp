# Finbourne.Sdk.Lusid.Model.CreateRelationshipRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the source entity. |
| **TargetEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the target entity. |
| **EffectiveFrom** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effective date of the relationship to be created |
| **EffectiveUntil** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effective datetime until which the relationship is valid. If not supplied this will be valid indefinitely. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateRelationshipRequest(
    sourceEntityId: ,  // required — The identifier of the source entity.
    targetEntityId: ,  // required — The identifier of the target entity.
    effectiveFrom: new DateTimeOrCutLabel(...),  // optional — The effective date of the relationship to be created
    effectiveUntil: new DateTimeOrCutLabel(...)  // optional — The effective datetime until which the relationship is valid. If not supplied this will be valid indefinitely.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateRelationshipRequest>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveFrom`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveUntil`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

