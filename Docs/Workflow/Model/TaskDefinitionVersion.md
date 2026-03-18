# Finbourne.Sdk.Workflow.Model.TaskDefinitionVersion

The version of the Task Definition used by this Task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtModified** | **DateTimeOffset** | Optional | The asAt datetime of the Task Definition used by this Task |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskDefinitionVersion(
    asAtModified: DateTimeOffset.Now  // optional — The asAt datetime of the Task Definition used by this Task
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskDefinitionVersion>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

