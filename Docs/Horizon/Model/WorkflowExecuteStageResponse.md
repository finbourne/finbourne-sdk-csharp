# Finbourne.Sdk.Horizon.Model.WorkflowExecuteStageResponse

One stage of a staged integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **Steps** | **List&lt;string&gt;** | Required | The steps that run for this stage. |
| **Parameters** | **List&lt;string&gt;** | Required | Names of every parameter this stage accepts. |
| **Rules** | **List&lt;string&gt;** | Required | Cross-field rules the stage enforces, in plain text. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new WorkflowExecuteStageResponse(
    name: "...",  // required
    steps: ,  // required — The steps that run for this stage.
    parameters: ,  // required — Names of every parameter this stage accepts.
    rules:   // required — Cross-field rules the stage enforces, in plain text.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowExecuteStageResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

