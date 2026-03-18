# Finbourne.Sdk.Workflow.Model.TaskActivity

Information about what tasks to create/update when receiving events

## oneOf Type

`TaskActivity` can be one of the following types:

* [CreateNewTaskActivity](./CreateNewTaskActivity.md)
* [UpdateMatchingTasksActivity](./UpdateMatchingTasksActivity.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new CreateNewTaskActivity(...);
var instance = new TaskActivity(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskActivity>(json);
```

## Related Models

- [CreateNewTaskActivity](./CreateNewTaskActivity.md)
- [UpdateMatchingTasksActivity](./UpdateMatchingTasksActivity.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

