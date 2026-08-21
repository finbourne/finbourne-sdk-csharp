# Finbourne.Sdk.Horizon.Model.WorkflowResultFieldsResponse

The result fields an instance returns to the Workflow task that started its run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceId** | **string** | Required | The instance these fields belong to. |
| **ReportsToWorkflow** | **bool** | Required | Whether this instance has an enabled RunWorkflow post-process task at all. |
| **ResultFields** | [List&lt;WorkflowResultFieldResponse&gt;](WorkflowResultFieldResponse.md) | Required | Every distinct field declared across this instance&#39;s RunWorkflow tasks. |
| **Tasks** | [List&lt;WorkflowResultFieldsTaskResponse&gt;](WorkflowResultFieldsTaskResponse.md) | Required | Per-task breakdown: an instance may declare different fields on success and on failure. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowResultFieldsResponse(
    instanceId: "...",  // required — The instance these fields belong to.
    reportsToWorkflow: true,  // required — Whether this instance has an enabled RunWorkflow post-process task at all.
    resultFields: new List<WorkflowResultFieldResponse>(),  // required — Every distinct field declared across this instance&#39;s RunWorkflow tasks.
    tasks: new List<WorkflowResultFieldsTaskResponse>()  // required — Per-task breakdown: an instance may declare different fields on success and on failure.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowResultFieldsResponse>(json);
```

- [WorkflowResultFieldResponse](WorkflowResultFieldResponse.md) — used in `ResultFields`
- [WorkflowResultFieldsTaskResponse](WorkflowResultFieldsTaskResponse.md) — used in `Tasks`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

