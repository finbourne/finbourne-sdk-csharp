# Finbourne.Sdk.Workflow.Model.UpdateTaskWithIdAndTriggerRequest

A request to update multiple Tasks Includes a trigger which is supplied from route in single update request
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskInstanceId** | **string** | Optional | The ID of the task instance |
| **CorrelationIds** | **List&lt;string&gt;** | Optional | A set of guid identifiers that allow correlation across the application tier |
| **Fields** | [List&lt;TaskInstanceField&gt;](TaskInstanceField.md) | Optional | Defines the fields associated with the update |
| **StackingKey** | **string** | Optional | The key for the Stack that this Task should be added to |
| **TriggerName** | **string** | Optional | The trigger we want to update the task with |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new UpdateTaskWithIdAndTriggerRequest(
    taskInstanceId: "...",  // optional — The ID of the task instance
    correlationIds: ,  // optional — A set of guid identifiers that allow correlation across the application tier
    fields: new List<TaskInstanceField>(),  // optional — Defines the fields associated with the update
    stackingKey: "...",  // optional — The key for the Stack that this Task should be added to
    triggerName: "..."  // optional — The trigger we want to update the task with
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateTaskWithIdAndTriggerRequest>(json);
```

- [TaskInstanceField](TaskInstanceField.md) — used in `Fields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

