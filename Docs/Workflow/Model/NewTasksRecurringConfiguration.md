# Finbourne.Sdk.Workflow.Model.NewTasksRecurringConfiguration

Behaviour applied to a new child task candidate whose stacking key matches an existing (non-terminal) child task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DoNotCreate** | **bool** | Optional | When true, the new child task will not be created |
| **InitialTriggerOverride** | **string** | Optional | When DoNotCreate is false, the new child task will be created with this trigger instead of the ChildTaskConfiguration&#39;s InitialTrigger |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new NewTasksRecurringConfiguration(
    doNotCreate: true,  // optional — When true, the new child task will not be created
    initialTriggerOverride: "..."  // optional — When DoNotCreate is false, the new child task will be created with this trigger instead of the ChildTaskConfiguration&#39;s InitialTrigger
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NewTasksRecurringConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

