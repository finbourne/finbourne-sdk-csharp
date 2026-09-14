# Finbourne.Sdk.Workflow.Model.ResultsRecurringConfiguration

Behaviour applied to new child task candidates, and to existing child tasks, when their stacking keys match one another
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NewTasks** | [NewTasksRecurringConfiguration](NewTasksRecurringConfiguration.md) | Required | *No description available.* |
| **ExistingTasks** | [ExistingTasksRecurringConfiguration](ExistingTasksRecurringConfiguration.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ResultsRecurringConfiguration(
    newTasks: new NewTasksRecurringConfiguration(...),  // required
    existingTasks: new ExistingTasksRecurringConfiguration(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultsRecurringConfiguration>(json);
```


## Related Models

- [NewTasksRecurringConfiguration](NewTasksRecurringConfiguration.md)
- [ExistingTasksRecurringConfiguration](ExistingTasksRecurringConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

