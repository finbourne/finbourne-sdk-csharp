# Finbourne.Sdk.Horizon.Model.WorkflowRunResultsResponse

A run's status and the result values it published, which is what the Workflow AQS polls while it waits for an integration it started to finish.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | **string** | Required | The run these results belong to, as returned by the execute endpoint. |
| **InstanceId** | **string** | Required | The instance that ran. |
| **Status** | **string** | Required | The run&#39;s status, reported exactly as the runs endpoint reports it: Queued, Started, Completed, Errored or Interrupted. A caller waiting for the run to finish is waiting for one of the last three. |
| **QueuedAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **StartedAt** | **DateTimeOffset?** | Optional | *No description available.* |
| **CompletedAt** | **DateTimeOffset?** | Optional | Null until the run reaches a terminal status. |
| **Attempt** | **int** | Required | Which attempt this run is, counting reruns of the same work. |
| **ReportsToWorkflow** | **bool** | Required | Whether this run was started by a Workflow task. False for a scheduled or file-triggered run, which publishes no results because nothing is waiting on them. |
| **Results** | [List&lt;WorkflowRunResultResponse&gt;](WorkflowRunResultResponse.md) | Required | One entry per field the instance declares, so the shape matches what the discovery endpoint promised when the worker was created. A declared field the run never published carries a null value. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowRunResultsResponse(
    runId: "...",  // required — The run these results belong to, as returned by the execute endpoint.
    instanceId: "...",  // required — The instance that ran.
    status: "...",  // required — The run&#39;s status, reported exactly as the runs endpoint reports it: Queued, Started, Completed, Errored or Interrupted. A caller waiting for the run to finish is waiting for one of the last three.
    queuedAt: DateTimeOffset.Now,  // optional
    startedAt: DateTimeOffset.Now,  // optional
    completedAt: DateTimeOffset.Now,  // optional — Null until the run reaches a terminal status.
    attempt: 0,  // required — Which attempt this run is, counting reruns of the same work.
    reportsToWorkflow: true,  // required — Whether this run was started by a Workflow task. False for a scheduled or file-triggered run, which publishes no results because nothing is waiting on them.
    results: new List<WorkflowRunResultResponse>()  // required — One entry per field the instance declares, so the shape matches what the discovery endpoint promised when the worker was created. A declared field the run never published carries a null value.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowRunResultsResponse>(json);
```

- [WorkflowRunResultResponse](WorkflowRunResultResponse.md) — used in `Results`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

