# Finbourne.Sdk.Lusid.Model.DeleteRelationshipRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the source entity of the relationship to be deleted. |
| **TargetEntityId** | **Dictionary&lt;string, string&gt;** | Required | The identifier of the target entity of the relationship to be deleted. |
| **EffectiveFrom** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effective date of the relationship to be deleted |
| **EffectiveUntil** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effective datetime until which the relationship will be deleted. If not supplied the deletion will be permanent. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeleteRelationshipRequest(
    sourceEntityId: ,  // required — The identifier of the source entity of the relationship to be deleted.
    targetEntityId: ,  // required — The identifier of the target entity of the relationship to be deleted.
    effectiveFrom: new DateTimeOrCutLabel(...),  // optional — The effective date of the relationship to be deleted
    effectiveUntil: new DateTimeOrCutLabel(...)  // optional — The effective datetime until which the relationship will be deleted. If not supplied the deletion will be permanent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeleteRelationshipRequest>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveFrom`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveUntil`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

