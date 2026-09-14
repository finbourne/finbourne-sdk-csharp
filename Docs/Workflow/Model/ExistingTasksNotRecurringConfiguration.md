# Finbourne.Sdk.Workflow.Model.ExistingTasksNotRecurringConfiguration

Behaviour applied to an existing (non-terminal) child task whose stacking key is not matched by any new child task candidate (i.e. it did not recur on this run)
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Trigger** | **string** | Optional | The existing task receives this trigger |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ExistingTasksNotRecurringConfiguration(
    trigger: "..."  // optional — The existing task receives this trigger
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExistingTasksNotRecurringConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

