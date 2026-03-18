# Finbourne.Sdk.Workflow.Model.TaskActivityResponse

Readonly information about how the worker should be executed

## oneOf Type

`TaskActivityResponse` can be one of the following types:

* [CreateNewTaskActivityResponse](./CreateNewTaskActivityResponse.md)
* [UpdateMatchingTasksActivityResponse](./UpdateMatchingTasksActivityResponse.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new CreateNewTaskActivityResponse(...);
var instance = new TaskActivityResponse(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskActivityResponse>(json);
```

## Related Models

- [CreateNewTaskActivityResponse](./CreateNewTaskActivityResponse.md)
- [UpdateMatchingTasksActivityResponse](./UpdateMatchingTasksActivityResponse.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

