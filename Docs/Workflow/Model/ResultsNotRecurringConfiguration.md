# Finbourne.Sdk.Workflow.Model.ResultsNotRecurringConfiguration

Behaviour applied when a new child task candidate's stacking key does not match any existing (non-terminal) child task, and to an existing child task whose stacking key is not matched by any new candidate
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExistingTasks** | [ExistingTasksNotRecurringConfiguration](ExistingTasksNotRecurringConfiguration.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ResultsNotRecurringConfiguration(
    existingTasks: new ExistingTasksNotRecurringConfiguration(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResultsNotRecurringConfiguration>(json);
```


## Related Models

- [ExistingTasksNotRecurringConfiguration](ExistingTasksNotRecurringConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

