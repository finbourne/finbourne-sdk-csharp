# Finbourne.Sdk.Workflow.Model.VersionedTaskDefinitionId

A Task Definition Id with an optional asAt timestamp identifying a specific version
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TaskDefinitionAsAt** | **DateTimeOffset?** | Optional | The asAt time of this version of the Task Definition. Null means the latest version. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new VersionedTaskDefinitionId(
    taskDefinitionId: new ResourceId(...),  // optional
    taskDefinitionAsAt: DateTimeOffset.Now  // optional — The asAt time of this version of the Task Definition. Null means the latest version.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VersionedTaskDefinitionId>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

