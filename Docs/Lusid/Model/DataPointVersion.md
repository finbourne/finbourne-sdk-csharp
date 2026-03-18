# Finbourne.Sdk.Lusid.Model.DataPointVersion

The version metadata for DataPoints.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtCreated** | **DateTimeOffset?** | Optional | The asAt datetime at which the entity was first created in LUSID. |
| **UserIdCreated** | **string** | Optional | The unique id of the user who created the entity. |
| **RequestIdCreated** | **string** | Optional | The unique request id of the command that created the entity. |
| **AsAtModified** | **DateTimeOffset?** | Optional | The asAt datetime at which the entity (including its properties) was last updated in LUSID. |
| **UserIdModified** | **string** | Optional | The unique id of the user who last updated the entity (including its properties) in LUSID. |
| **RequestIdModified** | **string** | Optional | The unique request id of the command that last updated the entity (including its properties) in LUSID. |
| **AsAtVersionNumber** | **int?** | Optional | The integer version number for the entity (the entity was created at version 1) |
| **EntityUniqueId** | **string** | Optional | The unique id of the entity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataPointVersion(
    asAtCreated: DateTimeOffset.Now,  // optional — The asAt datetime at which the entity was first created in LUSID.
    userIdCreated: "...",  // optional — The unique id of the user who created the entity.
    requestIdCreated: "...",  // optional — The unique request id of the command that created the entity.
    asAtModified: DateTimeOffset.Now,  // optional — The asAt datetime at which the entity (including its properties) was last updated in LUSID.
    userIdModified: "...",  // optional — The unique id of the user who last updated the entity (including its properties) in LUSID.
    requestIdModified: "...",  // optional — The unique request id of the command that last updated the entity (including its properties) in LUSID.
    asAtVersionNumber: 0,  // optional — The integer version number for the entity (the entity was created at version 1)
    entityUniqueId: "..."  // optional — The unique id of the entity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataPointVersion>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

