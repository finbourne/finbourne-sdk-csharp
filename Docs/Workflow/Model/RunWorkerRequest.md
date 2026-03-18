# Finbourne.Sdk.Workflow.Model.RunWorkerRequest

Request to Create a new worker
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Parameters** | [List&lt;ParameterValue&gt;](ParameterValue.md) | Required | The Parameter and their values. |
| **WorkerTimeout** | **int?** | Optional | The timeout in seconds for the worker |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new RunWorkerRequest(
    parameters: new List<ParameterValue>(),  // required — The Parameter and their values.
    workerTimeout: 0  // optional — The timeout in seconds for the worker
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunWorkerRequest>(json);
```


## Related Models

- [ParameterValue](ParameterValue.md) — used in `Parameters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

