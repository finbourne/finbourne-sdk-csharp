# Finbourne.Sdk.Workflow.Model.VersionInfo

The version metadata.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtCreated** | **DateTimeOffset?** | Optional | The asAt datetime at which this entity was first created. |
| **UserIdCreated** | **string** | Optional | The unique id of the user who created this entity. |
| **RequestIdCreated** | **string** | Optional | The request id of the request that created this entity. |
| **AsAtModified** | **DateTimeOffset?** | Optional | The asAt datetime at which this entity was last updated. |
| **UserIdModified** | **string** | Optional | The unique id of the user who last updated this entity. |
| **RequestIdModified** | **string** | Optional | The request id of the request that last updated this entity. |
| **AsAtVersionNumber** | **int?** | Optional | The integer version number for this entity (the entity was created at version 1). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new VersionInfo(
    asAtCreated: DateTimeOffset.Now,  // optional — The asAt datetime at which this entity was first created.
    userIdCreated: "...",  // optional — The unique id of the user who created this entity.
    requestIdCreated: "...",  // optional — The request id of the request that created this entity.
    asAtModified: DateTimeOffset.Now,  // optional — The asAt datetime at which this entity was last updated.
    userIdModified: "...",  // optional — The unique id of the user who last updated this entity.
    requestIdModified: "...",  // optional — The request id of the request that last updated this entity.
    asAtVersionNumber: 0  // optional — The integer version number for this entity (the entity was created at version 1).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionInfo>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

