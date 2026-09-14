# Finbourne.Sdk.Workflow.Model.ExistingTasksRecurringConfiguration

Behaviour applied to an existing (non-terminal) child task whose stacking key matches one or more new child task candidates
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IncrementAsAtModified** | **bool** | Optional | When true, the existing task&#39;s asAtModified is incremented even if no other change (Trigger or MergeFields) is applied |
| **Trigger** | **string** | Optional | The existing task receives this trigger |
| **MergeFields** | **List&lt;string&gt;** | Optional | The named fields on the existing task are updated with the values from the latest run. Only applies where the new-to-existing stacking key cardinality is one-to-one or one-to-many; unspecified fields are untouched. Data will be merged in even if these fields are in a read-only state. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new ExistingTasksRecurringConfiguration(
    incrementAsAtModified: true,  // optional — When true, the existing task&#39;s asAtModified is incremented even if no other change (Trigger or MergeFields) is applied
    trigger: "...",  // optional — The existing task receives this trigger
    mergeFields:   // optional — The named fields on the existing task are updated with the values from the latest run. Only applies where the new-to-existing stacking key cardinality is one-to-one or one-to-many; unspecified fields are untouched. Data will be merged in even if these fields are in a read-only state.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExistingTasksRecurringConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

