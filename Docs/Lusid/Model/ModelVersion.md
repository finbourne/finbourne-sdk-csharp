# Finbourne.Sdk.Lusid.Model.ModelVersion

The version metadata.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveFrom** | **DateTimeOffset** | Required | The effective datetime at which this version became valid. Only applies when a single entity is being interacted with. |
| **AsAtDate** | **DateTimeOffset** | Required | The asAt datetime at which the data was committed to LUSID. |
| **AsAtCreated** | **DateTimeOffset?** | Optional | The asAt datetime at which the entity was first created in LUSID. |
| **UserIdCreated** | **string** | Optional | The unique id of the user who created the entity. |
| **RequestIdCreated** | **string** | Optional | The unique request id of the command that created the entity. |
| **ReasonCreated** | **string** | Optional | The reason for an entity creation. |
| **AsAtModified** | **DateTimeOffset?** | Optional | The asAt datetime at which the entity (including its properties) was last updated in LUSID. |
| **UserIdModified** | **string** | Optional | The unique id of the user who last updated the entity (including its properties) in LUSID. |
| **RequestIdModified** | **string** | Optional | The unique request id of the command that last updated the entity (including its properties) in LUSID. |
| **ReasonModified** | **string** | Optional | The reason for an entity modification. |
| **AsAtVersionNumber** | **int?** | Optional | The integer version number for the entity (the entity was created at version 1) |
| **EntityUniqueId** | **string** | Optional | The unique id of the entity |
| **StagedModificationIdModified** | **string** | Optional | The ID of the staged change that resulted in the most recent modification. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ModelVersion(
    effectiveFrom: DateTimeOffset.Now,  // required — The effective datetime at which this version became valid. Only applies when a single entity is being interacted with.
    asAtDate: DateTimeOffset.Now,  // required — The asAt datetime at which the data was committed to LUSID.
    asAtCreated: DateTimeOffset.Now,  // optional — The asAt datetime at which the entity was first created in LUSID.
    userIdCreated: "...",  // optional — The unique id of the user who created the entity.
    requestIdCreated: "...",  // optional — The unique request id of the command that created the entity.
    reasonCreated: "...",  // optional — The reason for an entity creation.
    asAtModified: DateTimeOffset.Now,  // optional — The asAt datetime at which the entity (including its properties) was last updated in LUSID.
    userIdModified: "...",  // optional — The unique id of the user who last updated the entity (including its properties) in LUSID.
    requestIdModified: "...",  // optional — The unique request id of the command that last updated the entity (including its properties) in LUSID.
    reasonModified: "...",  // optional — The reason for an entity modification.
    asAtVersionNumber: 0,  // optional — The integer version number for the entity (the entity was created at version 1)
    entityUniqueId: "...",  // optional — The unique id of the entity
    stagedModificationIdModified: "..."  // optional — The ID of the staged change that resulted in the most recent modification.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ModelVersion>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

