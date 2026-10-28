# Finbourne.Sdk.Horizon.Model.WorkflowExecuteParametersResponse

The execute parameters a Workflow-driven integration instance accepts on executewithparams.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceId** | **string** | Required | The instance these parameters belong to. |
| **IntegrationType** | **string** | Required | The integration type of the instance, e.g. ta-tax-processes. |
| **Parameters** | [List&lt;WorkflowExecuteParameterResponse&gt;](WorkflowExecuteParameterResponse.md) | Required | Every parameter the integration accepts, each listed once. |
| **Stages** | [List&lt;WorkflowExecuteStageResponse&gt;](WorkflowExecuteStageResponse.md) | Required | Per-stage breakdown of the steps that run and the parameters accepted. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowExecuteParametersResponse(
    instanceId: "...",  // required — The instance these parameters belong to.
    integrationType: "...",  // required — The integration type of the instance, e.g. ta-tax-processes.
    parameters: new List<WorkflowExecuteParameterResponse>(),  // required — Every parameter the integration accepts, each listed once.
    stages: new List<WorkflowExecuteStageResponse>()  // required — Per-stage breakdown of the steps that run and the parameters accepted.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowExecuteParametersResponse>(json);
```

- [WorkflowExecuteParameterResponse](WorkflowExecuteParameterResponse.md) — used in `Parameters`
- [WorkflowExecuteStageResponse](WorkflowExecuteStageResponse.md) — used in `Stages`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

