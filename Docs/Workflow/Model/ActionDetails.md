# Finbourne.Sdk.Workflow.Model.ActionDetails

Abstracts the kinds of Actions available

## oneOf Type

`ActionDetails` can be one of the following types:

* [CreateChildTasksAction](./CreateChildTasksAction.md)
* [RunWorkerAction](./RunWorkerAction.md)
* [TriggerParentTaskAction](./TriggerParentTaskAction.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var inner = new CreateChildTasksAction(...);
var instance = new ActionDetails(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ActionDetails>(json);
```

## Related Models

- [CreateChildTasksAction](./CreateChildTasksAction.md)
- [RunWorkerAction](./RunWorkerAction.md)
- [TriggerParentTaskAction](./TriggerParentTaskAction.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

