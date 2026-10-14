# Finbourne.Sdk.Workflow.Model.LauncherEdge

Represents the relationship between a Launcher of a Workflow and the Task Definition it starts a run of
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LauncherId** | **string** | Optional | The identifier of the Launcher inside its Workflow |
| **TargetTaskDefinition** | [VersionedTaskDefinitionId](VersionedTaskDefinitionId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new LauncherEdge(
    launcherId: "...",  // optional — The identifier of the Launcher inside its Workflow
    targetTaskDefinition: new VersionedTaskDefinitionId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LauncherEdge>(json);
```

- [VersionedTaskDefinitionId](VersionedTaskDefinitionId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

