# Finbourne.Sdk.Workflow.Model.ChildTaskDefinitionEdge

Represents a parent-child relationship between two Task Definitions in a Workflow
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Parent** | [VersionedTaskDefinitionId](VersionedTaskDefinitionId.md) | Optional | *No description available.* |
| **Child** | [VersionedTaskDefinitionId](VersionedTaskDefinitionId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ChildTaskDefinitionEdge(
    parent: new VersionedTaskDefinitionId(...),  // optional
    child: new VersionedTaskDefinitionId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChildTaskDefinitionEdge>(json);
```


## Related Models

- [VersionedTaskDefinitionId](VersionedTaskDefinitionId.md)
- [VersionedTaskDefinitionId](VersionedTaskDefinitionId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

