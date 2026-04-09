# Finbourne.Sdk.Workflow.Model.CreateTaskRequest

Contains required info to create a new Task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CorrelationIds** | **List&lt;string&gt;** | Optional | A set of guid identifiers that allow correlation across the application tier |
| **Fields** | [List&lt;TaskInstanceField&gt;](TaskInstanceField.md) | Optional | Fields and their initial values - should correspond with the Task Definition field schema |
| **StackingKey** | **string** | Optional | The key for the Stack that this Task should be added to |
| **WorkflowId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateTaskRequest(
    taskDefinitionId: new ResourceId(...),  // optional
    correlationIds: ,  // optional — A set of guid identifiers that allow correlation across the application tier
    fields: new List<TaskInstanceField>(),  // optional — Fields and their initial values - should correspond with the Task Definition field schema
    stackingKey: "...",  // optional — The key for the Stack that this Task should be added to
    workflowId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateTaskRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaskInstanceField](TaskInstanceField.md) — used in `Fields`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

